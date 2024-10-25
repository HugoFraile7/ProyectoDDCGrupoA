# Preprocesado de datos
## Descripción de los métodos utilizados para la limpieza de datos estructurados (archivo: limpieza_estructurados)

## Carga y eliminación de duplicados:
- **Método**: Utilizamos **df.drop_duplicates()** para eliminar registros duplicados en el conjunto de datos.
- **Justificación**: Los duplicados pueden distorsionar el análisis y crear sesgos, por lo que es esencial eliminarlos.

## Extracción de información temporal y de ubicación:
- **Método**: A partir de la columna timestamp, se extrajeron las variables **country** y **timestamp**:
  **country**: extraída con str.extract(r'Reviewed in (.+?) on').
  **timestamp**: extraída con str.extract(r'on (.+)') y convertida a formato de fecha con **pd.to_datetime()**.
- **Justificación**: Esto permite trabajar con datos de fecha y país de forma separada, facilitando el análisis geográfico y temporal.

## Eliminación de columnas irrelevantes:
- **Método**: Eliminación de columnas con **df.drop(columns=[...])**, incluyendo:
Identificadores (**ID**, **product_name**, **etc**.).
Información redundante (**number_of_ratings**, **rating_out_of_5**, **brand**).
Especificaciones técnicas irrelevantes (**screen_size**, **cellular_technology**, etc.).
- **Justificación**: Estas columnas no son relevantes para el análisis de modelos de teléfonos y pueden confundir el análisis.

## Visualización y eliminación de datos faltantes:
- **Método**: Visualización de datos faltantes con un mapa de calor (**sns.heatmap**) y cálculo del porcentaje de valores faltantes (**df.isnull().sum()**).
Justificación: Nos permite identificar columnas con un alto porcentaje de datos faltantes, que luego se eliminan si son irrelevantes o muy incompletas.
Filtro de modelos específicos:
Método: Excluir ciertos valores de model_name usando **df[~df['model_name'].isin(...)]**.
- **Justificación**: Algunos modelos son irrelevantes para el análisis actual; se excluyen para mantener el enfoque en los datos importantes.


## Descripción de los métodos utilizados para la limpieza de datos no estructurados (archivo: tratamiento datos no estructurados)

## Detección de idioma:
- **Método**: Se utiliza la biblioteca **langdetect** para identificar el idioma en el que está escrito cada comentario. La función **detect_language()** intenta detectar el idioma de la reseña, y si no puede hacerlo, retorna **None**. Esta función se aplica a la columna **'review'** del DataFrame con **df['review'].apply(detect_language)**.
- **Justificación**: Detectar el idioma de los comentarios es útil para filtrar, agrupar o analizar los datos según el idioma. Esto es especialmente importante en datasets multilingües, donde el análisis debe ajustarse según el idioma para ser significativo o relevante. Además, identificar el idioma puede ayudar a realizar tareas específicas, como traducción automática o análisis de sentimiento, que pueden diferir entre idiomas.


## Filtrado de filas con idioma inglés:
- **Método**: Se cuenta el número de filas donde el valor de la columna **'language'** es **'en'** utilizando **(df['language'] == 'en').sum()**. Luego, se calcula el porcentaje de estas filas respecto al total con **count_en/len(df)**. Por último, se filtra el DataFrame para conservar solo las filas con idioma inglés mediante **df[df['language'] == 'en']**.
- **Justificación**: Este filtrado permite centrarse en los comentarios en inglés para análisis específicos, como análisis de sentimientos, ya que algunos métodos o bibliotecas funcionan mejor con datos en un idioma específico. Además, el análisis se vuelve más consistente al trabajar con un conjunto homogéneo de datos lingüísticos.


## Conversión de texto a minúsculas:
- **Método**: Se transforma el texto de la columna **'review'** a minúsculas utilizando **df_en['review'].str.lower()**.
- **Justificación**: Convertir el texto a minúsculas unifica el formato, lo cual es esencial para tareas de procesamiento de lenguaje natural, como la tokenización o la detección de palabras clave. Esto ayuda a evitar diferencias en el análisis causadas por la variación en el uso de mayúsculas y minúsculas.


## Tokenización de texto:
- **Método**: Se aplica la función **casual_tokenize** de **nltk.tokenize.casual** para dividir el texto en palabras o tokens. La tokenización se realiza sobre la columna **'review'**, y los resultados se almacenan en una nueva columna llamada **'tk_review'** mediante **df_en['review'].apply(casual_tokenize)**.
- **Justificación**: La tokenización es un paso fundamental en el procesamiento de texto, ya que convierte el texto en una lista de palabras o términos (tokens). Esto facilita tareas posteriores como el análisis de frecuencia de palabras, la eliminación de palabras irrelevantes (stopwords) y el análisis de sentimiento, permitiendo trabajar con el contenido textual de manera más estructurada.


## Eliminación de stopwords:
- **Método**: Se descargan las **stopwords** en inglés con **nltk.download('stopwords')**, y luego se crea un conjunto de estas palabras utilizando **set(nltk.corpus.stopwords.words('english'))**. A continuación, se eliminan las stopwords de los tokens en la columna **'tk_review'** mediante una función lambda que filtra las palabras que no están en el conjunto de **stopwords**.
- **Justificación**: Las **stopwords** son palabras comunes (como "the", "is", "and") que generalmente no aportan significado relevante en el análisis de texto. Eliminarlas reduce el ruido en los datos, mejora la precisión en tareas de procesamiento de lenguaje natural y ayuda a enfocarse en términos más significativos para el análisis.

## Descripción de los métodos utilizados para la limpieza de los datos de tipo fecha

## Conversión en nanosegundos:
- **Método**: Se crea una nueva columna llamada **'timestamp_nanosec'**, que contiene la representación en nanosegundos del **'timestamp'** mediante **data['timestamp'].astype('int64')**.
- **Justificación**: Se convierten las fechas a nanosegundos para así poder haces desplazamiento de las fechas de una manera más sencilla.

## Normalización del tiempo por modelo:
- **Método**: Se agrupan los datos por **'model_name'** y se restan los valores mínimos de **'timestamp_nanosec'** dentro de cada grupo, normalizando así los tiempos. Esto se realiza mediante **data.groupby('model_name')['timestamp_nanosec'].transform(lambda x: x - np.min(x))**, lo cual ajusta los valores de **'timestamp_nanosec'** para que comiencen desde cero para cada modelo.
- **Justificación**: Se normalizan los tiempos para así poder analizar como serie temporal todos los modelos independientemente de su fecha de salida.

## Formateo del timestamp:
- **Método**: Se actualiza la columna **'timestamp'** con el formato datetime a partir de **'timestamp_nanosec'** utilizando **pd.to_datetime(data['timestamp_nanosec'])**. A continuación, se crea una nueva columna llamada **'timestamp_formatted'**, que almacena la representación de la fecha en el formato **día/mes/año** mediante **data['timestamp'].dt.strftime('%d/%m/%Y')**.
- **Justificación**: Se da formato a las fechas para así hacer su interpretación más sencilla.

## Establecimiento del índice y ordenamiento de los datos:
- **Método**: Se establece la columna **'timestamp_formatted'** como índice del DataFrame utilizando **data.set_index('timestamp_formatted', inplace=True)**. Posteriormente, los datos se ordenan por la columna **'timestamp'** en orden ascendente mediante **data.sort_values(by='timestamp', ascending=True, inplace=True)**.
- **Justificación**: Se ordena según la fecha y se establece como íncide para hacer el análisis más sencillo.



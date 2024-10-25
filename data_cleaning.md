# Descripción de los métodos utilizados para la limpieza de datos

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

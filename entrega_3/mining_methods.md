# Mining Methods

## Descripción de las Técnicas Utilizadas

### 1. Análisis de Series Temporales
Se implementaron técnicas para procesar y analizar datos en series temporales. Los datos se agruparon por meses para simplificar el análisis y detectar patrones estacionales o tendencias generales.

- **Metodología**:
  - Conversión de fechas a un formato uniforme para garantizar consistencia.
  - Creación de un rango completo de fechas para identificar posibles días faltantes.
  - Agrupación de datos por meses, calculando métricas clave como promedios y recuentos para cada intervalo temporal.

- **Resultados**: Este enfoque permitió obtener una visión más clara de las tendencias mensuales, facilitando el análisis posterior y el modelado predictivo.

---

### 2. Modelado Predictivo con ARIMA
Se utilizó el modelo ARIMA para predecir valores futuros basados en la serie temporal mensual generada en el paso anterior. Este modelo permite capturar relaciones lineales, tendencias y patrones estacionales en los datos.

- **Metodología**:
  - Conversión de la serie temporal diaria a una mensual, calculando agregados para mantener la representatividad de los datos.
  - Análisis de las gráficas de autocorrelación (ACF) y autocorrelación parcial (PACF) para identificar el rango inicial de valores para los parámetros **p** (rezagos) y **q** (media móvil).
  - Exploración de todas las combinaciones posibles de hiperparámetros **(p, d, q)** dentro del rango identificado.
  - Evaluación de cada modelo en el conjunto de prueba, seleccionando el que minimizó el error cuadrático medio (MSE).

---

### 3. Análisis de Lenguaje Natural
En este proyecto, también exploramos el fascinante mundo del Procesamiento del Lenguaje Natural (PLN) para analizar datos textuales no estructurados. Si bien esta parte del análisis se planteó como un componente exploratorio, ofrece un potencial significativo para enriquecer los hallazgos generales.

- **Metodología**:
  - **Tokenización**: Dividimos el texto en palabras clave o tokens para facilitar el análisis.
  - **Análisis de Frecuencia**: Identificamos las palabras más comunes en los textos, extrayendo aquellas que podrían tener mayor relevancia en el contexto del proyecto.
  - **Limpieza de Datos**: Eliminamos palabras vacías (stop words), caracteres especiales y realizamos una normalización básica para garantizar la calidad del análisis.
  - **Visualización**: Utilizamos nubes de palabras (word clouds) para resaltar los términos más frecuentes y detectar patrones generales.

- **Resultados**: Este análisis permitió identificar temas recurrentes en los textos asociados, estableciendo una base para análisis futuros más complejos. Aunque preliminar, el enfoque de PLN aportó una perspectiva adicional que complementa el trabajo con series temporales.

---

## Justificación de la Selección de Técnicas

### Análisis de Series Temporales
Agrupar los datos por meses es esencial para capturar tendencias más amplias y patrones estacionales, que podrían no ser evidentes en una escala diaria. Este enfoque también reduce el ruido en los datos, mejorando la calidad del análisis y los resultados del modelado.

### Modelado Predictivo con ARIMA
ARIMA es ideal para series temporales con componentes estacionales y tendencias lineales. Su capacidad para modelar diferencias entre observaciones lo hace adecuado para datos agrupados en intervalos regulares, como meses. Además, el proceso de selección de hiperparámetros asegura que el modelo sea óptimo en términos de precisión predictiva.

### Análisis de Lenguaje Natural
Incorporar técnicas de PLN es una decisión estratégica para abordar los datos no estructurados. Aunque esta parte del análisis se encuentra en una etapa inicial, nos permitió abrir nuevas líneas de investigación para explorar correlaciones entre el contenido textual y las tendencias identificadas en las series temporales.

---

## Configuración de los Algoritmos

### Análisis de Series Temporales
- **Parámetros**:
  - Formato de fechas: `dayfirst=True` para garantizar la correcta interpretación de las fechas.
  - Frecuencia temporal: Mensual (`M`), obtenida agregando la serie diaria.
  - Métricas calculadas: Promedio y recuento de observaciones por mes.
- **Herramientas y Librerías**:
  - `pandas` para manipulación y agrupación de datos.
  - `matplotlib` para visualización básica.

### Modelado Predictivo con ARIMA
- **Selección de Hiperparámetros**:
  - **ACF (Autocorrelation Function)**: Utilizada para identificar valores iniciales del parámetro **q** (orden de la media móvil), evaluando la relación entre una observación y sus rezagos.
  - **PACF (Partial Autocorrelation Function)**: Utilizada para identificar valores iniciales del parámetro **p** (número de rezagos), evaluando la correlación directa entre una observación y sus rezagos, eliminando las correlaciones intermedias.
  - **Combinaciones probadas**: Se exploraron múltiples combinaciones de **p**, **d** y **q**, ajustando cada modelo y evaluándolo en el conjunto de prueba.
  - **Modelo seleccionado**: El modelo con el menor error cuadrático medio (MSE) en el conjunto de prueba fue elegido como el mejor.
- **Hiperparámetros finales**:
  - **p**: [Valor seleccionado basado en PACF].
  - **d**: 1, para eliminar tendencias y estabilizar la serie.
  - **q**: [Valor seleccionado basado en ACF].
- **Herramientas y Librerías**:
  - `statsmodels` para implementar y ajustar el modelo ARIMA.
  - `scikit-learn` para calcular métricas de evaluación como el MSE.
  - `matplotlib` para visualizar predicciones y evaluar el desempeño del modelo.

### Análisis de Lenguaje Natural
- **Parámetros**:
  - Stop words eliminadas: Idiomas aplicados: [especificar idiomas].
  - Tipo de normalización: Conversión a minúsculas y eliminación de caracteres especiales.
- **Herramientas y Librerías**:
  - `nltk` para tokenización y limpieza de textos.
  - `wordcloud` para visualización de nubes de palabras.
  - `pandas` para preprocesamiento y análisis básico.

---

## Conclusión
El análisis combinó la potencia de las series temporales y el modelado predictivo con un enfoque preliminar en el análisis de lenguaje natural. Esto no solo permitió extraer patrones de los datos estructurados, sino también explorar los datos textuales, sentando las bases para un análisis más profundo en futuras iteraciones. Este enfoque integral asegura que los hallazgos sean robustos, relevantes y versátiles.

Objetivo General del Proyecto
El objetivo de este proyecto es analizar la evolución de la percepción de los usuarios sobre dispositivos móviles de la marca Apple en Amazon, a lo largo del tiempo, mediante el uso de análisis de sentimiento en sus reseñas. A través de la extracción y procesamiento de las reviews de Amazon y datos de lanzamiento de los dispositivos, se busca identificar si las opiniones de los usuarios tienden a volverse más negativas conforme pasa el tiempo desde la salida del dispositivo, evaluando si existe una correlación entre el paso del tiempo y la disminución de la satisfacción.

Preguntas de Investigación o Hipótesis
Las preguntas de investigación e hipótesis clave que este proyecto pretende explorar son:

¿Existe una tendencia en las opiniones de los usuarios que se vuelva más negativa a medida que transcurre el tiempo desde el lanzamiento de un dispositivo de Apple?
¿Cómo varía el sentimiento general de las reseñas a lo largo del ciclo de vida de un dispositivo?
¿Se observan cambios en la valoración de las características específicas (como batería, calidad de cámara, etc.) que podrían ser indicativos de obsolescencia percibida?
Estas preguntas tienen como fin identificar patrones que puedan indicar una "obsolescencia psicológica", donde los usuarios se sientan menos satisfechos con el tiempo, aunque el dispositivo siga siendo funcional.

Justificación de los Datos Seleccionados
Para abordar estas preguntas, seleccionamos dos conjuntos de datos principales:

Reviews de Amazon: Contienen opiniones de usuarios que han comprado y usado los dispositivos Apple, reflejando la experiencia real y la percepción subjetiva de los consumidores. La cantidad y variabilidad de estas reseñas permiten analizar el sentimiento en torno a los dispositivos a lo largo de su vida en el mercado.
Dataset de dispositivos móviles (CSV): Este conjunto de datos contiene información estructurada sobre cada modelo de dispositivo Apple (fechas de lanzamiento, especificaciones, etc.). Esto permite relacionar cada review con la fecha de salida del dispositivo correspondiente, lo cual es esencial para analizar la evolución del sentimiento en función del tiempo desde el lanzamiento.
Estos datos específicos son relevantes y necesarios para responder nuestras preguntas de investigación, ya que brindan la base sobre la cual medir los cambios en las reseñas de usuarios desde una perspectiva longitudinal.

Desafíos Potenciales con los Datos Limpiados
Duplicación de Datos: Durante el proceso de scrapping, se generaron duplicados de reviews que sesgan los resultados hacia las fechas más recientes, creando una concentración artificial de datos. Este problema puede introducir un sesgo temporal en el análisis de sentimiento, haciéndolo parecer más reciente de lo que realmente es.

Falta de Reseñas Iniciales: En muchos casos, faltan reseñas cercanas a la fecha de lanzamiento de algunos dispositivos, lo que dificulta el análisis de los primeros meses de recepción del producto en el mercado. Esta limitación podría hacer que se pierdan tendencias tempranas que expliquen cambios en la percepción de los usuarios.

Sesgo de Disponibilidad Temporal: Dado que las reseñas más recientes suelen ser más abundantes, el análisis podría mostrar una percepción negativa del dispositivo simplemente debido al sesgo temporal en los datos (más reviews en fechas cercanas), en lugar de una tendencia real en la opinión de los usuarios.

Calidad del Análisis de Sentimiento: El análisis de sentimiento en español puede tener limitaciones, como la falta de precisión en la detección de sarcasmo o en el entendimiento de frases complejas, lo que podría afectar la calidad de los resultados.

Estos desafíos serán tenidos en cuenta al interpretar los resultados para asegurar que cualquier conclusión se base en datos procesados de manera adecuada y en su contexto de recopilación.
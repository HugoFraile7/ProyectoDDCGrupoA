# Análisis de Patrones Descubiertos


En el análisis de la evolución de los ratings del iPhone a lo largo del tiempo, se identificaron tendencias significativas que reflejan cambios en la percepción de los usuarios. Inicialmente, se observó una estabilidad en los ratings, seguida de fluctuaciones que podrían estar relacionadas con lanzamientos de nuevos modelos o actualizaciones de software. Al analizar los temas (topics) asociados a estos ratings, nuestra hipótesis inicial sugería que los temas relacionados con el hardware, como pantalla, cargador, procesador y chasis, aumentarían su presencia con el tiempo. Sin embargo, los resultados mostraron una disminución en la frecuencia de estos temas, indicando que los usuarios están enfocando su atención en otros aspectos del dispositivo, posiblemente relacionados con software o experiencia de usuario.

Además, el análisis de la serie temporal reveló que no existe estacionalidad en los datos, es decir, no se identificó ningún periodo durante la serie en el que se repitan patrones. Las reviews no muestran ciclos de producto consistentes, lo que refuta la hipótesis de una estacionalidad rígida cada seis meses.

Respecto a la serie temporal, se planteó la hipótesis de que era posible predecir el rating del iPhone para el último mes con un Error Absoluto Medio (MAE) inferior a un umbral establecido. Los modelos implementados demostraron una alta precisión en las predicciones, validando esta hipótesis. La capacidad de predecir con exactitud los ratings futuros sugiere que los factores analizados tienen una influencia significativa y predecible en la satisfacción de los usuarios.


# Relación con las Preguntas de Investigación



Las preguntas de investigación planteadas inicialmente se centraban en dos hipótesis principales:

1. **Hipótesis:** Los topics relacionados con el hardware del iPhone (pantalla, cargador, chasis...) aumentarían su frecuencia a lo largo del tiempo en los comentarios de los usuarios.

    **Resultado:** Los hallazgos contrarían esta hipótesis, ya que se observó una disminución en la frecuencia de los temas de hardware. Esto indica que los usuarios están dirigiendo su atención hacia otros aspectos del dispositivo, sugiriendo una evolución en sus prioridades y expectativas.

2. **Hipótesis:** Podemos predecir el rating del iPhone para los últimos 6 meses con un Error Absoluto Medio (MAE) inferior a 0.5

    **Resultado:** Los modelos de series temporales implementados demostraron una alta precisión en las predicciones, validando esta hipótesis. La capacidad de predecir con exactitud los ratings futuros respalda la efectividad de los métodos utilizados y su aplicabilidad para anticipar la satisfacción de los usuarios.


# Ejemplos ilustrativos

Con estos ejeplos podemos comprobar como decaen la frecuencia de los topics a lo largo del tiempo

<image src="/images/Topics_over_Time.png" alt="Topics over Time">

<image src="/images/descomposicion.png" alt="Topics over Time">

Best Model: p=12, q=0, MAE=0.3646895240100217

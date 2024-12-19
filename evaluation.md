# Evaluación de Modelos de Series Temporales

## Evaluación del Modelo ARMA

El mejor modelo ARMA es autorregresivo con un orden \( p = 12 \).

### 1. AIC (Akaike Information Criterion)
El AIC mide la calidad del modelo ajustado, penalizando la complejidad para evitar el sobreajuste. Valores más bajos indican un mejor equilibrio entre ajuste y simplicidad.  
**Interpretación**: El AIC de **156.903** sugiere un modelo razonablemente ajustado con buena parsimonia.

### 2. BIC (Bayesian Information Criterion)
El BIC evalúa la calidad del modelo como el AIC, pero con una penalización más estricta para modelos complejos. Valores más bajos indican un modelo mejor.  
**Interpretación**: El BIC de **184.749** indica un ajuste aceptable, aunque ligeramente menos favorable comparado con el AIC.

### 3. Log likelihood
El logaritmo de verosimilitud refleja qué tan probable es que los datos observados provengan del modelo ajustado. Valores más altos son mejores.  
**Interpretación**: El valor de **-64.452** muestra un ajuste decente del modelo a los datos.

### 4. MAE sobre el test
El MAE mide el error absoluto promedio en la predicción, siendo un indicador directo de precisión. Valores más bajos son mejores.  
**Interpretación**: El MAE de **0.36468** indica un desempeño predecible y preciso del modelo sobre los datos de prueba.

---

## Evaluación del Modelo SARIMA

El mejor modelo SARIMA tiene un orden autorregresivo \( p = 23 \), una estacionalidad de 6 meses y \( Q = 6 \).

### 1. AIC (Akaike Information Criterion)
El AIC mide el equilibrio entre el ajuste y la complejidad del modelo. Valores más bajos son mejores.  
**Interpretación**: El AIC de **179.438** sugiere que el modelo SARIMA es menos eficiente que el ARMA en términos de balance entre ajuste y complejidad.

### 2. BIC (Bayesian Information Criterion)
El BIC penaliza modelos complejos más que el AIC, con valores más bajos indicando mejor desempeño.  
**Interpretación**: El BIC de **229.163** sugiere que este modelo es más complejo y menos eficiente en comparación con el ARMA.

### 3. Log likelihood
Un logaritmo de verosimilitud más alto refleja un modelo que se ajusta mejor a los datos observados.  
**Interpretación**: El valor de **-64.719** es similar al del ARMA, indicando un ajuste comparable pero no significativamente mejor.

### 4. MAE sobre el test
El MAE mide el error absoluto promedio y representa la precisión en la predicción. Valores más bajos son preferibles.  
**Interpretación**: El MAE de **0.3904** muestra que el modelo SARIMA tiene un desempeño ligeramente peor en comparación con el ARMA sobre los datos de prueba.

---
## Comparación de los modelos
A pesar de que, al ver el seasonal descompose, creíamos que habría una cierta estacionalidad, bien cada 6 meses o bien cada 12, al probar el modelo todas las métricas son mejores para el modelo autorregresivo. Es decir, no merece la pena tratar la serie como estacional. En los valores AIC y BIC como además se penaliza la complejidad del modelo, el modelo con estacionalidad y un valor mayor de p, es decir, parámetros más complejos.
Cabe recalcar que estos modelos han sido escogidos usando el criterio del MAE sobre el test (últimos 6 meses). Este criterio hace que los valores de p tiendan a ser más altos, sin embargo, hemos considerado que era mejor mirar el error únicamente y no penalizar demasiado la complejidad del modelo.
## Evaluación Bert
En el modelo de tópicos dinámicos obtenidos utilizando Bert se ha calculado la diversidad de los tópicos. Para ello se han fijado en 10 el top de palabras del tópico. Esto indica que el 75% de las palabras de los tópicos son únicas. Esto es un buen indicador, puesto que, nos muestra que hay una diversidad alta en los tópicos. Además, se observa poca redundandia entre las palabras claves de los tópicos. Esta métrica es útil para observar la evolución de los tópicos, ya que, al estar diferenciados entre sí, se pueden observar tópicos más característicos.


## Evaluación del Modelo ARMA
El mejor modelo Sarma es el autorregresivo de p igual a 12.
### 1. AIC (Akaike Information Criterion)
- Valor obtenido: 156.903 
### 2. BIC (Bayesian Information Criterion)
- Valor obtenido: 184.749
### 3. Log likelihood
- Valor obtenido: -64.452
### 4. MAE sobre el test
- Valor obtenido: 0.36468
## Evaluación del Modelo SARIMA
El mejor modelo Sarima obtenido entre los parámetros probados es el autorregresivo con p=23, una estacionalidad de 6 meses, es decir, medio año y un Q de 6. Este modelo ha obtenido las siguiente métricas
### 1. AIC (Akaike Information Criterion)
- Valor obtenido: 179.438 
### 2. BIC (Bayesian Information Criterion)
- Valor obtenido: 229.163
### 3. Log likelihood
- Valor obtenido: -64.719
### 4. MAE sobre el test
- Valor obtenido: 0.3904
## Comparación de los modelos
A pesar de que, al ver el seasonal descompose, creíamos que habría una cierta estacionalidad, bien cada 6 meses o bien cada 12, al probar el modelo todas las métricas son mejores para el modelo autorregresivo. Es decir, no merece la pena tratar la serie como estacional. En los valores AIC y BIC como además se penaliza la complejidad del modelo, el modelo con estacionalidad y un valor mayor de p, es decir, parámetros más complejos.
Cabe recalcar que estos modelos han sido escogidos usando el criterio del MAE sobre el test (últimos 6 meses). Este criterio hace que los valores de p tiendan a ser más altos, sin embargo, hemos considerado que era mejor mirar el error únicamente y no penalizar demasiado la complejidad del modelo.
## Evaluación Bert
### 1. Diversidad de tópicos
En el modelo de tópicos dinámicos obtenidos utilizando Bert se ha calculado la diversidad de los tópicos. Para ello se han fijado en 10 el top de palabras del tópico. Esto indica que el 75% de las palabras de los tópicos son únicas. Esto es un buen indicador, puesto que, nos muestra que hay una diversidad alta en los tópicos. Además, se observa poca redundandia entre las palabras claves de los tópicos. Esta métrica es útil para observar la evolución de los tópicos, ya que, al estar diferenciados entre sí, se pueden observar tópicos más característicos.
### 2. Perplexity del modelo
Usando las probabilidades que asigna bert a cada palabra dentro de los tópicos se ha obtenido la perplexity del modelo dando un valor de 231.7842. La perplexity es una métrica que mide la incertidumbre a la hora de predecir tópicos. El valor obtenido es un valor medio, es decir, no tiene demasiado ajuste.

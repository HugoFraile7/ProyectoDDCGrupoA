## Análisis de estacionariedad de la serie temporal

Para comprobar si la serie es estacionaria, utilizamos el método *Dickey-Fuller aumentado (ADF)*. Los resultados obtenidos fueron los siguientes:

•⁠  ⁠*ADF Statistic:* -6.5117  
•⁠  ⁠*p-value:* 1.0964e-08  
•⁠  ⁠*Valores críticos:*  
  - Nivel de significancia del 1%: -3.5444  
  - Nivel de significancia del 5%: -2.9111  
  - Nivel de significancia del 10%: -2.5932  

Dado que el p-valor es menor a 0.05, rechazamos la hipótesis nula, lo que indica que la serie es estacionaria.

![Descomposición estacional](seasonal_descompose.png)
En el seasonal descompose vemos como claramente se repite un patrón a lo largo del tiempo.

## Selección del modelo ARMA

En primer lugar, se probó un modelo *ARMA* evaluando todas las posibles combinaciones de parámetros. Tras realizar la comparación, se determinó que el mejor modelo, basado en el menor *MAE* (Error Absoluto Medio), es el modelo autorregresivo con *p = 12*.

•⁠  ⁠*MAE obtenido en el conjunto de test:* 0.365
![Predicción Arma](arima.png)

## Selección del modelo SARMA

El mejor modelo *SARMA* encontrado tiene las siguientes características:

•⁠  ⁠*Orden:* (23, 0, 0)  
•⁠  ⁠*Orden estacional:* (0, 0, 1, 6)  
•⁠  ⁠*MAE:* 0.3905  

A pesar de ser el mejor modelo SARMA, sus resultados son inferiores al modelo ARMA previamente seleccionado, que obtuvo un *MAE* de 0.365 en el conjunto de test.
![Predicción Sarma](Sarma.png)

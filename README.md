# Bitcoin Forecaster

Se creo este predictor de bitcoin utilizando la Api de Bitso y facebookProphet para poder predecir los precios 15 días en adelante.

## Paso 1.-
Hacer llamadas a la Api de Bitso para obtener nuestro primer data frame con el cual trabajaremos posteriormente.
Empezamos a recopilar información a partir del 1 de enero del 2019.
Esta información contiene el precio, el día, el mes, el año y cual fue la posición de mercado que mas predomino.
Guardamos esta información en archivo csv para poder utilizarla despues.

## Paso 2.-
Creamos una función que trabaje con el data frame creado en el paso 1 y extraiga de la información guardada por minuto 
lo siguiente:

La fecha con el formatio día/mes/año. 
Dos medías de precio, una de 24 horas y otra de 12 horas. 
El precio mínimo del día y el precio máximo.

Nuestro data frame original tenía más de 300k registros y lo reducimos a 350 registros, lo ideal es tener 365 registros por año.

## Paso 3.-
... POR ESCRIBIR

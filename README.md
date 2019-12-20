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
Creamos una función que obtenga las fechas en las cuales existe un cambio de tendencia. Este cambio lo conocemos al crear 
un data frame con dummies para las ventas y compras.

## Paso 4.-
Creamos funciones que calculen el MAPE error, un inversor de coxbox y un comparador de dataframes para comparar el data frame historico con el que nos entrega prophet de facebook.

## Paso 5.-
Creamos una copia del data frame del paso 2. Y la columna de precios la pasamos a través de la función coxplox de scipy.
Entrenamos el modelo de prophet utilizando los changepoints del paso 3. Creamos un future data frame con 15 días y este data frame que nos entrega prophet lo pasamos por las funciones creadas en el paso 4, para regresar a los valores originales del precio del BTC y conocer nuestro MAPE error con el comparador de dataframes.

## Paso 6.-
Por último creamos una función que genere una gráfica con la información del nuevo data frame donde podamos conocer las predicciones del Bitcoin y nos diga cual es el precio de compra sugerido, precio de venta sugerido y el máximo posible para el día de hoy.

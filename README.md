# Bitcoin Forecaster

Se creó este predictor de Bitcoin/Pesos Mexicanos utilizando la Api de Bitso y FacebookProphet para poder predecir los precios de dicha moneda 15 días en adelante a partir de hoy*.

## Paso 1.-
Hacer llamadas a la Api de Bitso para obtener nuestro primer data frame con el cuál trabajaremos posteriormente.
Empezamos a recopilar información a partir del 1 de enero del 2019.*
Ésta información contiene: el precio, el día, el mes, el año y cuál fue la posición de mercado que más predominó.
Guardamos ésta información en un archivo formato .csv para poder utilizarla después.

## Paso 2.-
Creamos una función que trabaje con el data frame creado en el paso 1 y extraiga de la información guardada por minuto 
lo siguiente:

La fecha con el formatio día/mes/año. 
Dos medías de precio, una de 24 horas y otra de 12 horas. 
El precio mínimo y máximo del día. 

Nuestro data frame original tenía más de 300 mil filas y lo reducimos a 350, lo ideal es tener 365 filas por año.

## Paso 3.-
Creamos una función que obtenga las fechas en las cuáles existe un cambio de tendencia. Este cambio lo conocemos al crear 
un data frame con dummies para las ventas y compras.

## Paso 4.-
Creamos funciones que calculen el MAPE error, un inversor de coxbox y un comparador de dataframes para comparar el data frame histórico con el que nos entrega Facebookprophet.

## Paso 5.-
## 5.1
Creamos una copia del data frame del paso 2. 
## 5.2
La columna de precios la pasamos a través de la función coxplox de scipy.
## 5.3
Entrenamos el modelo de prophet utilizando los changepoints del paso 3. 
## 5.4
Creamos un future data frame con 15 días y este data frame que nos entrega prophet lo pasamos por las funciones creadas en el paso 4, para regresar a los valores originales del precio del BTC y conocer nuestro MAPE error con el comparador de dataframes.

## Paso 6.-
Por último creamos una función que genere una gráfica con la información del nuevo data frame donde podamos conocer las predicciones del Bitcoin y nos diga cuál es el precio de compra y precio de venta sugerido, tambíen el máximo posible que puede alcanzar*.

**
1. El día de hoy es a partir de que el usuario corre el programa y se guarda el archivo .html con la predicción.
2. En la carpeta csv_files se encuentra el archivo historic_data.csv el cuál contiene la información histórica a partir del 1 de enero del 2019 hasta la fecha del último commit realizado a este repositorio.
3. El máximo posible se refiere a cada día creado en la predicción.

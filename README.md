# Conceptos de Estadistica Avanzada

Pruebas de normalidad, medidas estadísticas como varianza y desviación estándar, así como el concepto de linealidad aplicado a un ejemplo sobre como predecir el precio de venta de casas de acuerdo a sus diferentes características.

Comenzamos cargando los datos a utilizar
<br>![image](https://github.com/user-attachments/assets/ef9b242a-954d-42d1-a359-3ece8903aef3)

Limpiamos los datos y nos quedamos solo con las variables numéricas
<br>![image](https://github.com/user-attachments/assets/666dc660-e3b0-41ae-a1b4-2ad79fd6f1ff)

Podemos utilizar la función describe para obtener la media, desviación estándar y la información de los cuartiles para cada variable
<br>![image](https://github.com/user-attachments/assets/ae6101d9-9f15-4d34-9037-cea2783476e1)

Analizando algunas de las variables podemos ver que tienen distribución logarítmica y normal como:
<br>***GrLivArea***
<br>![image](https://github.com/user-attachments/assets/d50ddb86-b4cd-4ce3-9612-def1e7ef4112)

***SalePrice***
<br>![image](https://github.com/user-attachments/assets/bddbb865-3cab-4c01-86f6-8e6abbe543c0)

***2ndFlrSF***
<br>![image](https://github.com/user-attachments/assets/7190efa1-b07b-414f-8ff4-6b2ec643ba6a)

Revisando la correlación entre las variables podemos obtener el siguiente heatmap
<br>![image](https://github.com/user-attachments/assets/c73280c2-94e2-4ab3-9049-f2b615dd042f)
<br>La variable que más se relaciona con el precio de venta es la calidad general (OverallQual) con 79%

Para realizar una prueba OLS separamos el precio de venta de las demás variables por ser la que mas nos interesa
<br>![image](https://github.com/user-attachments/assets/c27dc19c-500e-4e48-b773-ea7fa332f557)
![image](https://github.com/user-attachments/assets/c0d228d8-d487-4cf7-892e-dd9fec8c2dbb)
<br>![image](https://github.com/user-attachments/assets/4844b511-d405-48a1-b65b-62c908761023)

Basándonos en el valor p, las variables mas significativas son MSSubClass LotArea OverallQual OverallCond YearBuilt MasVnrArea BsmtFinSF1 TotalBsmtSF 1stFlrSF 2ndFlrSF GrLivArea BsmtFullBath BedroomAbvGr KitchenAbvGr TotRmsAbvGrd Fireplaces GarageYrBlt GarageCars WoodDeckSF ScreenPorch

Tomamos las variables con un valor p menor a 0.5
<br>![image](https://github.com/user-attachments/assets/e5c05be5-ccf1-421b-b6ab-24655ab1a36b)

Calculamos el factor de inflación de la varianza de las variables restantes
<br>![image](https://github.com/user-attachments/assets/af3e0033-b259-4c4b-ab76-99bdba32b07f)

Las variables que presentan multicolinealidad, son 1stFlrSF, 2ndFlrSF, GrLivArea

Volvemos a realizar otra prueba de OLS eliminando estas variables
<br>![image](https://github.com/user-attachments/assets/95b9469a-5224-47df-ae54-d0226942e8f7)
<br>![image](https://github.com/user-attachments/assets/5ddc5a7e-d1c1-44bb-9c57-6f2ff48da097)

El valor de R-cuadrada baja un poco después de realizar los métodos de limpieza pero no significativamente, el error cuadrático medio sigue siendo muy alto en comparación con los datos lo que puede significar que los datos no se estén ajustando correctamente al modelo.

Error cuadrático medio (MSE): 1326912420.4375734

R-squared: 0.795 | Adj. R-squared: 0.793

# README — Proceso ETL y Análisis de Churn en TelecomX

Este documento describe el flujo completo de Extracción, Transformación y Carga (ETL), junto con el análisis exploratorio aplicado al dataset de clientes de TelecomX.

# 1. Requisitos
Antes de ejecutar el script, instala las siguientes librerías:
pip install / pandas / numpy / requests / matplotlib / seaborn / plotly / dataframe_image

# 2. Extracción de Datos
## 2.1 Importación de librerías
Se cargan los módulos necesarios para manipulación de datos y solicitudes HTTP.
## 2.2 Descarga del dataset
Los datos se obtienen desde un archivo JSON alojado en GitHub mediante requests.

## 2.3 Conversión a DataFrame
El JSON descargado se transforma en un DataFrame de pandas para su manipulación.

# 3. Normalización de Datos
El dataset contiene columnas anidadas (customer, phone, internet, account). Se normalizan usando pd.json_normalize.
Posteriormente, todos los DataFrames normalizados se concatenan junto con las columnas principales (customerID, Churn).

# 4. Transformación de Datos
## 4.1 Revisión de columnas tipo object
Se inspeccionan valores únicos para detectar inconsistencias.

## 4.2 Corrección de valores vacíos
Se reemplazan valores vacíos en Churn por Unknown.

## 4.3 Revisión de columnas numéricas
Se verifica el tipo de datos y se limpian valores no numéricos en Charges.Total.

# 5. Diccionario de Datos
En esta sección se incluyen únicamente los términos que están presentes en el diccionario adjunto al proyecto.

# 6. Análisis Estadístico
Se generan estadísticas descriptivas para las variables numéricas principales (tenure, Charges.Monthly, Charges.Total) y se exportan como imagen.

# 7. Análisis de Churn
Se calcula la distribución de clientes según su estado de abandono y se genera un gráfico de torta.

# 8. Análisis Categórico
Se analizan todas las variables categóricas mediante:

Gráficos de barras (countplot)
Gráficos apilados normalizados por categoría
Ambos análisis se exportan como imágenes.

# 9. Análisis Numérico
Se generan boxplots para comparar la distribución de variables numéricas según el estado de Churn.

# 10. Resultados Exportados
El proyecto genera las siguientes imágenes:

tabla_stats_descriptivas.png
tabla_abandono.png
resumen_global_churn.png
analisis_categorico_churn.png
proporciones_categoricas_churn.png
distribucion_numerica_churn.png

# 11. Conclusiones
En este apartado de dejan expresadas las principales conclusiones del analisis.

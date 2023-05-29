# Project-IV: ZARA Join Life Visualization

## Descripción 
Este proyecto tiene como objetivo podemos analizar y comparar los precios, las composiciones y el etiquetado ecológico de los artículos de ropa de Zara para determinar cuáles son los artículos de ropa de Zara más asequibles y sostenibles.


## Database
Este database proporciona información sobre el precio, la composición y el etiquetado ecológico de las prendas de vestir de Zara conocido como Join Life. En concreto, incluye códigos de artículos, nombres, descripciones, títulos de vida conjunta, descripciones de vida conjunta, precios de artículos y composiciones.

**DataFrames iniciales:**

1. DataFrame composition: contiene información relativa a la composición de materiales de cada artículo
    - item_code: *int*, foreign key referenciando los artículos
    - part_name: *str*, parte de la prenda (Exterior/Forro)
    - material: *str*, nombre del material
    - percent: *str*, porcentaje del material relativo a la parte de la prenda


2. DataFrame items: contiene información relativa a los artículos como precio, codigo articulo, nombre, descripción, tipo de etiquetaje (eco-label or not)
    - item_code: *int*, código numérico asignado a cada artículo de ropa (primary key)
    - item_name: *str*, nombre del artículo
    - item_desc: *str*, descripción del artículo 
    - join_life: *bool*, si el artículo lleva o no etiqueta ecológica
    - joinlife_title: *str*, ecologic marking
    - joinlife_desc: *str*, descripción de la acción ecológica llevada a cabo 
    - item_price: *num*, precio del artículo en céntimos de €

A partir de estos, se crean otros dos  dataframe:

3. Dataframe estandares_min_eco: incluye los tipos de materiales ecológicos y el porcentaje mínimo de composición del material en una prenda para que sea calificada como sostenible, es decir, que forme parte de la línea Join Life de Zara. Se ha extraído manualmente de la columna joinlife_title del dataframe items.

4. Dataframe composition eco_label: a partir de un merge de composition y items mediante la primary key de item_code, obtenemos un dataframe nuevo que incluye las columnas de composition y la columna join_life para observar qué composición de materiales tienen las prendas según el etiquetaje ecológico o no ecológico. 



## Workflow 
**Data aquisition:** Para llevar a cabo este estudio, los datos han sido extraídos del data set [Fast Fashion Eco-Data](https://www.kaggle.com/datasets/thedevastator/fast-fashion-eco-data?select=fastFasionItemsDim.csv) en Kaggle que tiene como fecha noviembre del 2020.

**Data management:** Los datos han sido transformados y limpiados con la librería pandas y regex. 

**Data analysis:** Para realizar el análisis, se han importado los dataframes 1,2 y 3 a Power BI Desktop. Des de Power BI se ha creado el dataframe 4. A partir de estos dataframes, se han realizado visualizaciones para representar los datos y probar las hipótesis. 

**Conclusiones**: Extraer conclusiones en base al resultado de las visualizaciones.


## Organización
El repositorio consiste de: 
- README file
- Data/: incluye dos subcarpetas donde se encuentran los csv originales (raw) y los csv transformados (clean) después de la limpieza de datos
- cleaning.ipynb: este jupyter notebook contiene el código para la limpieza
- images/: imágenes usadas para el reporte y dashboard 
- visualization.pbix: archivo de Power BI Desktop con las visualizaciones recogidas en un único dashboard

![imagen](/images/captura_dashboard.png)















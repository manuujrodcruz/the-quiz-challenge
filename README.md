# Dashboard Interactivo para Análisis de Métricas de The Quiz Challenge

Este repositorio contiene el desarrollo de un dashboard interactivo y un modelo de minería de datos creado como proyecto final para la asignatura **Inteligencia de Negocios**. El objetivo es analizar las métricas del canal de YouTube **The Quiz Challenge** para identificar patrones que maximicen las vistas y los suscriptores, ayudando a los creadores a tomar decisiones estratégicas basadas en datos.

## Objetivo del Proyecto

El propósito principal del proyecto es diseñar un dashboard interactivo que visualice métricas clave del canal, como vistas, suscriptores, visualizaciones por país, por edad, y días de la semana con mayor audiencia, además de identificar qué tipos de contenido generan mayor interacción. Para ello, se implementó un modelo de clustering que agrupa videos similares según sus características, proporcionando insights sobre las temáticas más exitosas.

## Metodología

El proyecto se desarrolló en las siguientes etapas:

1. **Análisis Inicial de Datos**: Se trabajó con un conjunto de datos inicial (`video_data_for_clustering.csv`) proporcionado por YouTube Analytics, que incluía métricas como vistas, tiempo de reproducción, suscriptores, duración promedio de vistas, impresiones, y tasa de clics. Se revisaron estas métricas para entender su relevancia.

2. **Preprocesamiento de Datos**: Utilizando **Tableau Prep** y **Excel**, se limpiaron y organizaron los datos. Se vincularon las métricas a los videos asumiendo que las estadísticas entre dos fechas corresponden al video más cercano a la fecha inicial. Además, se enriquecieron los datos con columnas adicionales extraídas de la API de YouTube, como:
   - **Categoría**: Para clasificar videos por temáticas.
   - **is_short**: Para identificar si son YouTube Shorts o videos normales.
   - **has_emojis** y **has_hashtags**: Para detectar emojis o hashtags en los títulos.
   - **country_with_max_views**: Para identificar el país con más vistas.
   - **total_subscriptions** y **total_subscription_loss**: Para analizar el flujo de suscripciones.

3. **Análisis de Clustering**: Se implementó un modelo de clustering (K-Means) en **Python** utilizando bibliotecas como **Pandas**, **Matplotlib**, **Scikit-learn** (StandardScaler, PCA, KMeans, LabelEncoder, silhouette_score). Este modelo agrupó los videos en cuatro clústeres según métricas numéricas y categóricas, revelando patrones en el rendimiento del contenido.

4. **Desarrollo del Dashboard**: Con **Tableau**, se creó un dashboard interactivo que permite explorar métricas como vistas por país, por edad, días de la semana con mayor audiencia, y el impacto de las temáticas identificadas por el clustering.

## Resultados

El análisis reveló cuatro clústeres de videos con patrones distintivos:

- **Cluster 0**: Videos interactivos tipo "Would You Rather" y de cultura pop, con altas vistas y tasas de clics.
- **Cluster 1**: Videos sobre deportes, destacados por un alto número de vistas.
- **Cluster 2**: Videos cortos relacionados con deportes y naturaleza, efectivos para captar atención rápida.
- **Cluster 3**: Contenido sobre cultura pop y geografía, que resalta el interés en temas culturales.

El dashboard permite a **The Quiz Challenge** visualizar estas métricas de forma clara y tomar decisiones informadas sobre qué tipo de contenido priorizar. Los resultados se guardaron en archivos como `videos_por_cluster.csv` para su análisis posterior.

## Estructura del Repositorio

- `/data`: Contiene el dataset a utilizar en el notebook (`video_data_for_clustering.csv`).
- `/scripts`: Scripts en Python para preprocesamiento, clustering y generación de gráficos (ej. `clustering_latest.ipynb`).
- `/visualizations`: Archivos de Tableau con el dashboard interactivo.
- `/docs`: Documentación adicional, incluyendo el archivo `ProyectoFinal.pdf`, que detalla los requisitos y entregables del proyecto.

## Herramientas Utilizadas

- **Tableau Prep**: Para la limpieza y transformación de datos.
- **Tableau**: Para la creación del dashboard interactivo.
- **Excel**: Para la visualización inicial y manejo de archivos CSV.
- **Python**: Para el análisis de clustering y gráficos, con bibliotecas como:
  - Pandas
  - Matplotlib
  - Scikit-learn (StandardScaler, PCA, KMeans, LabelEncoder, silhouette_score)
- **API de YouTube**: Para la extracción de datos adicionales.

## Contribuciones

Este proyecto fue desarrollado por:

- **Manuel José Rodríguez Cruz**
- **Steven Manuel Mateo Ramos**
- **José Antonio Taveras Abreu**

Agradecemos cualquier comentario o sugerencia para mejorar el proyecto.

## Instrucciones de Uso

1. Clona este repositorio: `git clone [URL del repositorio]`.
2. Explora los scripts en `/scripts` para revisar el proceso de clustering (`clustering_latest.ipynb`).
3. Abre los archivos en `/visualizations` con Tableau para interactuar con el dashboard.
4. Revisa los datasets en `/data` para analizar los datos procesados.
5. Consulta el archivo `ProyectoFinal.pdf` en `/docs` para conocer los detalles de los requisitos del proyecto.

## Recomendaciones Estratégicas

- Priorizar contenido interactivo tipo "Would You Rather" y temas de cultura pop, que muestran alto engagement.
- Explorar más videos cortos (YouTube Shorts) relacionados con deportes y naturaleza.
- Monitorear continuamente las métricas por país y edad para adaptar el contenido a las preferencias de la audiencia.

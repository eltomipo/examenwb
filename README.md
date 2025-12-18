# examenwb
Predicción del Nivel de PIB utilizando Datos del Banco Mundial
El objetivo de este proyecto es predecir el nivel de PIB de distintos países a partir de indicadores económicos, sociales y demográficos obtenidos del Banco Mundial.

El trabajo debe realizarse en tres etapas principales:

Etapa 1: Análisis descriptivo e imputación de datos

Etapa 2: Reducción de dimensionalidad con PCA

Etapa 3: Modelación mediante algoritmos de clasificación
Etapa 1: Análisis Descriptivo e Imputación de Datos
Revisión general del dataset

Identificar el número de países, años y variables disponibles.

Número total de observaciones

Porcentaje de datos faltantes por variable: En caso que la variable cuente con menos de un 15% de datos NA se recomienda imputar. En caso contrario, eliminar variable.

Identificación de outliers relevantes

Otras observaciones relevantes.
Etapa 2: Reducción de Dimensionalidad con PCA
En esta fase del proyecto, nos enfrentamos a un dataset con una alta densidad de información macroeconómica y demográfica. Trabajar con demasiadas variables puede generar el problema de la dimensionalidad, donde el ruido de los datos dificulta el rendimiento de los modelos de clasificación.

Para optimizar nuestro análisis, aplicaremos la técnica de Análisis de Componentes Principales (PCA). Este método estadístico transforma el conjunto original de variables correlacionadas en un nuevo conjunto de variables no correlacionadas llamadas Componentes Principales.

Metodología Adoptada

Preparación y Estandarización: Dado que variables como el PIB y el Crecimiento Poblacional manejan escalas drásticamente distintas, se seleccionarán únicamente las columnas numéricas para aplicar una estandarización. Esto garantiza que el PCA no se sesgue hacia las variables con magnitudes numéricas más altas.

Extracción de Varianza: Se ejecutará el algoritmo PCA para identificar cuánto aporte informativo ofrece cada nueva componente. Utilizaremos el gráfico de varianza acumulada para visualizar este impacto.

Criterio de Selección: Siguiendo las mejores prácticas, seleccionaremos el número mínimo de componentes necesarias para retener entre el 70% y el 90% de la varianza total. Este rango permite simplificar significativamente el modelo sin perder los patrones esenciales que explican las diferencias entre países.

Generación del Insumo: El resultado final será un nuevo DataFrame compuesto por estas componentes principales. Este "dataset reducido" servirá como la base de entrenamiento para nuestros futuros modelos de clasificación, permitiendo una ejecución más eficiente y una mejor generalización de los resultados.

Etapa Final: Implementación y Comparación de Modelos de Clasificación

En esta etapa final del proyecto se procede a la implementación de modelos de clasificación, con el propósito de evaluar el efecto de la reducción de dimensionalidad sobre el desempeño predictivo y la estructura del problema. Las fases de proyecto son las siguientes:

En primer lugar, se construyen dos modelos de clasificación utilizando el conjunto de datos original, es decir, considerando la totalidad de las variables explicativas sin aplicar técnicas de reducción de dimensionalidad. Esta aproximación permite establecer una línea base (baseline) para el análisis comparativo posterior.
Posteriormente, se desarrollan los mismos modelos de clasificación empleando como variables de entrada las componentes principales obtenidas en la etapa de reducción de dimensionalidad mediante PCA. De esta forma, se evalúa si la representación reducida de los datos logra preservar información relevante para la tarea de clasificación.
Ambos enfoques se implementan bajo condiciones metodológicas comparables, manteniendo criterios consistentes de partición de datos y métricas de evaluación. El desempeño de los modelos se analiza mediante indicadores adecuados al problema de clasificación, permitiendo contrastar los resultados obtenidos con datos originales y con datos reducidos.

Finalmente, se realiza un análisis comparativo de los resultados, discutiendo las ventajas y limitaciones de cada enfoque, así como el impacto del uso de PCA en términos de desempeño, interpretabilidad y complejidad del modelo. Esta etapa cierra el proyecto integrando los aprendizajes obtenidos a lo largo de las fases previas y fundamentando las decisiones analíticas adoptadas.

# Predicción de Riesgo Genético - Pipeline de Machine Learning

## Descripción del Proyecto
Este proyecto simula un caso de estudio para un laboratorio de bioinformática que busca predecir la predisposición de pacientes a una enfermedad genética. El modelo predictivo se construye utilizando un conjunto de datos en formato CSV que incluye biomarcadores genéticos, variables clínicas y factores ambientales.

## Tecnologías Utilizadas
* **Lenguaje:** Python
* **Librerías principales:** `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`

## Fases del Pipeline de Machine Learning
El desarrollo del proyecto sigue un flujo de trabajo estructurado para el procesamiento de datos y el entrenamiento del modelo predictivo[cite: 4]:

1. **Análisis Exploratorio y Carga de Datos:** * Carga del archivo CSV en un DataFrame de pandas y exploración de sus dimensiones, tipos de datos y valores faltantes.
2. **Limpieza y Preprocesamiento:**
   * Imputación de valores nulos utilizando la media para las variables numéricas y la moda (el valor más frecuente) para las variables categóricas.
   * odificación de variables categóricas ordinales.
   * Detección y eliminación de valores atípicos (outliers) utilizando la técnica del Rango Intercuartílico (IQR) en variables clave como colesterol, IMC, glucosa y los marcadores genéticos 3 y 5.
3. **Transformación de Datos:**
   * Estandarización de las características numéricas utilizando `StandardScaler`.
   * Reducción de dimensionalidad aplicando Análisis de Componentes Principales (PCA), configurado para retener el 95% de la varianza explicada.
4. **Modelado y Evaluación:**
   * División del dataset en conjuntos de entrenamiento (80%) y prueba (20%).
   * Entrenamiento de un modelo de clasificación K-Nearest Neighbors (KNN) alimentado por los componentes principales generados por PCA.
   * Evaluación exhaustiva del modelo utilizando métricas como el *Accuracy* (Precisión), la Matriz de Confusión y el *Classification Report*.
   * Análisis final sobre el número de componentes principales resultantes.

## Conceptos Teóricos Abordados
Además de la implementación práctica, este proyecto sirve para explorar conceptos fundamentales de Machine Learning:
* La importancia del tratamiento adecuado de valores faltantes antes de entrenar un modelo.
* La necesidad crítica de utilizar `StandardScaler` en algoritmos basados en el cálculo de distancias, como es el caso de KNN.
* [cite_start]Cómo el PCA ayuda a mitigar la maldición de la dimensionalidad y las ventajas de aplicarlo antes de un modelo KNN[cite: 19, 22].
* [cite_start]Las consecuencias en el rendimiento del modelo si se elimina demasiada varianza durante la reducción de dimensionalidad[cite: 21].

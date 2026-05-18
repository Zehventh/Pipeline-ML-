# Predicción de Riesgo Genético - Pipeline de Machine Learning

## Descripción del Proyecto
[cite_start]Este proyecto simula un caso de estudio para un laboratorio de bioinformática que busca predecir la predisposición de pacientes a una enfermedad genética[cite: 2]. [cite_start]El modelo predictivo se construye utilizando un conjunto de datos en formato CSV que incluye biomarcadores genéticos, variables clínicas y factores ambientales[cite: 2, 3].

## Tecnologías Utilizadas
* **Lenguaje:** Python
* **Librerías principales:** `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`

## Fases del Pipeline de Machine Learning
[cite_start]El desarrollo del proyecto sigue un flujo de trabajo estructurado para el procesamiento de datos y el entrenamiento del modelo predictivo[cite: 4]:

1. [cite_start]**Análisis Exploratorio y Carga de Datos:** * Carga del archivo CSV en un DataFrame de pandas y exploración de sus dimensiones, tipos de datos y valores faltantes[cite: 5, 6].
2. **Limpieza y Preprocesamiento:**
   * [cite_start]Imputación de valores nulos utilizando la media para las variables numéricas y la moda (el valor más frecuente) para las variables categóricas[cite: 7].
   * [cite_start]Codificación de variables categóricas ordinales[cite: 8].
   * [cite_start]Detección y eliminación de valores atípicos (outliers) utilizando la técnica del Rango Intercuartílico (IQR) en variables clave como colesterol, IMC, glucosa y los marcadores genéticos 3 y 5[cite: 9].
3. **Transformación de Datos:**
   * [cite_start]Estandarización de las características numéricas utilizando `StandardScaler`[cite: 10].
   * [cite_start]Reducción de dimensionalidad aplicando Análisis de Componentes Principales (PCA), configurado para retener el 95% de la varianza explicada[cite: 11].
4. **Modelado y Evaluación:**
   * [cite_start]División del dataset en conjuntos de entrenamiento (80%) y prueba (20%)[cite: 12].
   * [cite_start]Entrenamiento de un modelo de clasificación K-Nearest Neighbors (KNN) alimentado por los componentes principales generados por PCA[cite: 13].
   * [cite_start]Evaluación exhaustiva del modelo utilizando métricas como el *Accuracy* (Precisión), la Matriz de Confusión y el *Classification Report*[cite: 14].
   * [cite_start]Análisis final sobre el número de componentes principales resultantes[cite: 15].

## Conceptos Teóricos Abordados
[cite_start]Además de la implementación práctica, este proyecto sirve para explorar conceptos fundamentales de Machine Learning[cite: 16]:
* [cite_start]La importancia del tratamiento adecuado de valores faltantes antes de entrenar un modelo[cite: 17].
* [cite_start]La necesidad crítica de utilizar `StandardScaler` en algoritmos basados en el cálculo de distancias, como es el caso de KNN[cite: 18].
* [cite_start]Cómo el PCA ayuda a mitigar la maldición de la dimensionalidad y las ventajas de aplicarlo antes de un modelo KNN[cite: 19, 22].
* [cite_start]Las consecuencias en el rendimiento del modelo si se elimina demasiada varianza durante la reducción de dimensionalidad[cite: 21].

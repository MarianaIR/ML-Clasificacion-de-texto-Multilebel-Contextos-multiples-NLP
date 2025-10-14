# 📖 CLASIFICACIÓN DE TEXTO MULTILABEL: CONTEXTOS MÚLTIPLES EN NLP

[![Python](https://img.shields.io/badge/Python-3670A0?style=flat&logo=python&logoColor=ffdd54)](https://www.python.org/)  
[![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)](https://numpy.org/)  
[![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)](https://pandas.pydata.org/)  
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)  
[![Sklearn-Multilearn](https://img.shields.io/badge/Sklearn--Multilearn-1C3668?style=flat&logo=python&logoColor=white)](http://scikit-multilearn.github.io/)  
[![Matplotlib](https://img.shields.io/badge/Matplotlib-11557c?style=flat&logo=matplotlib&logoColor=white)](https://matplotlib.org/)  
[![Seaborn](https://img.shields.io/badge/Seaborn-0099CC?style=flat&logo=seaborn&logoColor=white)](https://seaborn.pydata.org/)

Este proyecto se centra en el **desarrollo y evaluación de modelos de Clasificación de Texto Multietiqueta (Multi-label)** aplicando enfoques de **Procesamiento de Lenguaje Natural (NLP)** y librerías especializadas para abordar escenarios donde una instancia puede pertenecer a múltiples categorías simultáneamente.

---

## 🧠 Contenido del Proyecto

### 1️⃣ Preparación de Datos y NLP
- Carga del *dataset* de **preguntas de Stack Overflow** (`stackoverflow_preguntas.csv`).
- Vectorización de las preguntas utilizando **`TfidfVectorizer`** (con 5000 *features*).
- Transformación de las etiquetas (`Tags`) a formato de matriz binaria/dispersa para clasificación *multi-label*.
- División de datos en conjuntos de entrenamiento y prueba.

### 2️⃣ Entrenamiento de Modelos
- Implementación de algoritmos de clasificación *multi-label*:  
  - **Relevancia Binaria (Binary Relevance - BR):** Utilizando `OneVsRestClassifier` (con `LogisticRegression`).
  - **Clasificador ML-KNN:** Algoritmo adaptado de `skmultilearn` que resuelve el problema *multi-label* de forma directa.
- **Estrategia de Contextos Múltiples:** Se comparan los enfoques para determinar la mejor estrategia para la clasificación de múltiples etiquetas.

### 3️⃣ Evaluación del Sistema
- Cálculo de métricas de rendimiento, siendo la principal:  
  - **Hamming Loss:** Mide la fracción de etiquetas predichas incorrectamente (un valor más cercano a **0** es mejor).
  - **Precisión.**
- Análisis comparativo de la capacidad de los modelos para **sugerir etiquetas** que, aunque no fueron puestas por el usuario, son relevantes (lo que sugiere un rendimiento **mejor que el etiquetado humano**).

---

## 🛠️ Librerías Utilizadas

| Librería       | Uso principal                               |
|----------------|---------------------------------------------|
| **NumPy**      | Cálculos numéricos y manipulación de arrays |
| **Pandas**     | Manipulación y análisis de datos tabulares  |
| **Scikit-learn** | Vectorización (`TfidfVectorizer`), modelos base (`LogisticRegression`), métricas y `OneVsRestClassifier` |
| **Scikit-multilearn** | Implementación de clasificadores *multi-label* como **ML-KNN** y **BinaryRelevance** |
| **Matplotlib / Seaborn** | Visualización de datos y análisis exploratorio/resultados |

---

## 🎯 Objetivo del Proyecto
Aplicar y comparar diferentes metodologías de **clasificación *multi-label*** en un conjunto de datos real de preguntas técnicas (Stack Overflow) para predecir múltiples etiquetas relevantes, optimizando la precisión de las clasificaciones y demostrando la superioridad de los modelos especializados sobre el etiquetado manual en ciertos contextos.

---

## 📈 Resultados Esperados
- Obtención de un **Hamming Loss bajo** para validar la precisión de la clasificación (ej. 0.07 para `OneVsRestClassifier`).
- Demostración de la **efectividad de los clasificadores adaptados** (*ML-KNN* y *Binary Relevance*).
- **Validación del modelo** como una herramienta capaz de identificar y sugerir etiquetas contextualmente válidas que el usuario pudo haber omitido.

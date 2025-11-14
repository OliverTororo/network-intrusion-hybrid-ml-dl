# 🛡️ IDS Hybrid Pipeline — CICIDS2017 (Multiclass + SMOTE Full)

## 📄 Notebook: `ids_hybrid_pipeline_colab_full_smote.ipynb`

Este repositorio contiene un notebook completamente documentado para entrenar y evaluar un **Sistema de Detección de Intrusiones (IDS)** basado en **Machine Learning + Deep Learning**, utilizando el dataset **CICIDS2017** bajo la siguiente configuración experimental:

```python
DATASET = 'CICIDS2017'
TASK_MODE = 'multiclass'
SMOTE_MODE = 'full'

```

El notebook está optimizado para **Google Colab** y ejecuta un pipeline completo, generando métricas, gráficas y modelos entrenados (ML y DL).

----------

## 🔧 Variables Globales del Notebook

El comportamiento del pipeline se controla mediante la modificación de estas tres variables al inicio del notebook.

### 1. 🔹 DATASET

Define el conjunto de datos a cargar.

Python

```
DATASET = 'CICIDS2017'

```

-   **Función:** Esta variable asegura la correcta ruta de carga, limpieza, preprocesamiento y definición de clases para el dataset **CICIDS2017**.
    

### 2. 🔹 TASK_MODE

Define el tipo de problema de clasificación que resolverá el pipeline.

Python

```
TASK_MODE = 'multiclass'

```

-   **Valores Típicos:** `'binary'` o `'multiclass'`.
    
-   **Configuración Actual:** Usando `'multiclass'`, el código se ajusta automáticamente para manejar todas las clases de ataque de CICIDS2017.
    
-   **Clases en Multiclase (CICIDS2017):**
    
    -   BENIGN
        
    -   DoS Hulk, PortScan, DDoS, GoldenEye
        
    -   FTP-Patator, SSH-Patator
        
    -   Slowloris, Slowhttptest
        
    -   Bot
        
    -   Web Attack – Brute Force, Web Attack – XSS, Web Attack – Sql Injection
        
    -   Infiltration, Heartbleed
        

### 3. 🔹 SMOTE_MODE

Controla la aplicación del oversampling (**SMOTE**) para tratar el desbalanceo de clases.

Python

```
SMOTE_MODE = 'full'

```

-   **Valores Típicos:** `"none"`, `"minority"` o `"full"`.
    
-   **Configuración Actual:** Usando `"full"` se garantiza el balanceo de todas las clases minoritarias, mejorando el **Recall** y el **F1-score** para ataques poco frecuentes.
    

----------

## 🧩 Funcionalidades y Componentes del Pipeline

### 1️⃣ Preprocesamiento de Datos

-   Carga del dataset CICIDS2017 desde Google Drive.
    
-   Limpieza y eliminación de columnas irrelevantes o corruptas.
    
-   Codificación y normalización de _features_.
    
-   División en conjuntos de entrenamiento y prueba.
    
-   **Balanceo de Clases:** Aplicación de **SMOTE Full** sobre el conjunto de entrenamiento.
    

### 2️⃣ Modelos de Machine Learning (ML)

El pipeline entrena y evalúa los siguientes algoritmos:

-   **Random Forest (RF)**
    
-   **Decision Tree (DT)**
    
-   **K-Nearest Neighbors (KNN)**
    
-   **Multi-Layer Perceptron (MLP)**
    
-   **CatBoost**
    
-   **LightGBM**
    

**Resultados:** Se generan métricas (Accuracy, Precision, Recall, F1-score, AUC), tiempos de ejecución y una Matriz de Confusión por modelo.

### 3️⃣ Modelos de Deep Learning (DL)

Se implementan arquitecturas avanzadas para detección de intrusiones:

-   **ANN** (Artificial Neural Network)
    
-   **1D-CNN** (1D Convolutional Neural Network)
    
-   **LSTM** (Long Short-Term Memory)
    
-   **Autoencoder + Logistic Regression (AE-LR)**
    

**Características:** Se utilizan _Callbacks_ (`EarlyStopping`, `ModelCheckpoint`) para optimizar el entrenamiento.

### 4️⃣ Visualizaciones Clave

El notebook genera automáticamente:

-   Matrices de confusión multiclase.
    
-   Curvas ROC.
    
-   Gráficos comparativos de métricas (F1-score, Accuracy, AUC) entre todos los modelos.
    

----------

## 🚀 Cómo Ejecutar el Notebook en Google Colab

1.  Sube el archivo `ids_hybrid_pipeline_colab_full_smote.ipynb` a tu **Google Drive**.
    
2.  Ábrelo con Google Colab.
    
3.  **Monta tu Google Drive** para acceder a los datos:
    
    Python
    
    ```
    from google.colab import drive
    drive.mount('/content/drive')
    
    ```
    
4.  Verifica o ajusta las variables de configuración al inicio.
    
5.  **Ejecuta todos los bloques en orden.**
    

----------

## 🧪 Requisitos Principales

**Categoría**

**Bibliotecas**

**Básicas**

`numpy`, `pandas`, `matplotlib`, `seaborn`, `scikit-learn`

**Balanceo**

`imbalanced-learn`

**ML Avanzado**

`xgboost`, `lightgbm`, `catboost`

**Deep Learning**

`tensorflow / keras`

----------

## 👨‍💻 Autor y Licencia

Jordy Oliver Flores Loayza

Estudiante de Ingeniería de Sistemas de Información — UPC (Perú)

**Proyecto:** Sistema de Detección de Intrusiones Basado en Machine Learning para la Protección de Redes Educativas en Instituciones Escolares Peruanas.

Este proyecto se distribuye bajo la **Licencia MIT**.

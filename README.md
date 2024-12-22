# Clasificación de Cáncer usando Redes Neuronales

## Resumen Detallado

### 1. Cargar el dataset
- Se utiliza `pandas` para cargar un archivo CSV llamado `"cancer.csv"`.
- Las columnas se separan en:
  - **Características (`x`)**: Todos los datos excepto la columna de diagnóstico.
  - **Etiqueta (`y`)**: La columna `diagnosis(1=m, 0=b)` que indica si el caso es maligno o benigno.

### 2. Dividir el dataset
- Se usa `train_test_split` de `sklearn` para dividir los datos en:
  - **Datos de entrenamiento (80%)**: `x_train` y `y_train`.
  - **Datos de prueba (20%)**: `x_test` y `y_test`.

### 3. Crear y configurar la red neuronal
- Se usa TensorFlow (`tf.keras`) para definir un modelo secuencial.
- La red tiene:
  1. **Capa de entrada**: Con 256 neuronas y activación "sigmoid".
  2. **Capa oculta**: Con 256 neuronas y activación "sigmoid".
  3. **Capa de salida**: Con 1 neurona y activación "sigmoid" para salida binaria.
- Se compila con:
  - **Optimizador**: "adam" para optimización eficiente.
  - **Pérdida**: `binary_crossentropy`, adecuada para clasificación binaria.
  - **Métrica**: "accuracy" para evaluar el rendimiento.

### 4. Entrenamiento del modelo
- El modelo se entrena durante 1000 épocas en los datos de entrenamiento (`x_train`, `y_train`).
- Se muestra la pérdida y la precisión en cada época.

### 5. Evaluación del modelo
- Se evalúa el modelo en los datos de prueba (`x_test`, `y_test`).
- Devuelve:
  - **Pérdida**: `0.1893` (baja, indica buen ajuste).
  - **Precisión**: `93.86%` (alta, indica buen desempeño).

## Objetivo principal
Predecir si un caso es maligno o benigno a partir de características biomédicas, utilizando una red neuronal completamente conectada. El modelo logra una precisión del `93.86%` en los datos de prueba.

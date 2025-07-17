# Análisis de Enfermedad Cardíaca con XGBoost

  **Autor**: Carolina Melero

  ## Descripción
  Análisis completo de predicción de enfermedad cardíaca utilizando XGBoost como modelo principal, con optimización de hiperparámetros mediante GridSearchCV.

  ## Dataset
  - **Registros**: 920 pacientes de múltiples centros médicos
  - **Variables**: 15 características clínicas (edad, sexo, tipo de dolor en pecho, presión arterial, colesterol, etc.)
  - **Variable objetivo**: Presencia de enfermedad cardíaca (binario: 0=No, 1=Sí)
  - **Valores faltantes**: Principalmente en dataset VA Long Beach (manejados con imputación)

  ## Proceso Realizado

  ### 1. Exploración Inicial
  - Análisis de estructura del dataset y tipos de datos
  - Identificación de valores faltantes por centro médico
  - Detección de outliers en variables numéricas
  - Conversión de variable objetivo multiclase a binaria

  ### 2. Análisis Exploratorio (EDA)
  - Estadísticas descriptivas detalladas
  - Visualizaciones: histogramas, gráficos de barras, matriz de correlación
  - Análisis de distribución por clase objetivo
  - Identificación de relaciones entre variables

  ### 3. Preprocesamiento
  - Imputación de valores faltantes (mediana para numéricas, constante para categóricas)
  - One-Hot Encoding para variables categóricas
  - Escalado estándar para variables numéricas
  - Tratamiento de outliers con capping en percentiles extremos
  - División estratificada: 80% entrenamiento, 20% prueba

  ### 4. Modelado con XGBoost

  #### Modelo Base
  - n_estimators: 100
  - max_depth: 3
  - learning_rate: 0.1
  - **F1-Score**: 0.8468

  #### Modelo Optimizado (GridSearchCV)
  - Búsqueda exhaustiva en 36 combinaciones de parámetros
  - Validación cruzada con 5 folds
  - Mejores parámetros encontrados
  - **F1-Score**: 0.8571
  - **ROC-AUC**: 0.9163

  ## Resultados

  ### Métricas Comparativas
  | Métrica | Modelo Base | Modelo Optimizado | Mejora |
  |---------|-------------|-------------------|---------|
  | Accuracy | 0.8478 | 0.8587 | +0.0109 |
  | Precision | 0.8571 | 0.8659 | +0.0088 |
  | Recall | 0.8361 | 0.8484 | +0.0123 |
  | F1-Score | 0.8468 | 0.8571 | +0.0103 |
  | ROC-AUC | 0.9077 | 0.9163 | +0.0086 |

  ### Mejora en F1-Score: 1.2%

  ## Variables Más Importantes
  1. Características relacionadas con ejercicio (thalch, exang)
  2. Tipo de dolor en el pecho (cp)
  3. Depresión ST inducida por ejercicio (oldpeak)
  4. Edad y sexo del paciente

  ## Aplicaciones Prácticas
  - Sistema de screening para identificar pacientes en riesgo
  - Herramienta de apoyo en decisiones clínicas
  - Priorización de pacientes para pruebas diagnósticas adicionales
  - Implementación en sistemas de alerta temprana

  ## Archivos Generados
  - `Heart_Disease_XGBoost.ipynb`: Notebook completo con análisis y código
  - `README_Heart_Disease_XGBoost.md`: Este archivo de resumen

  ## Requisitos
  - pandas, numpy, matplotlib, seaborn
  - scikit-learn
  - xgboost

  ## Conclusión
  El modelo XGBoost optimizado logra un excelente desempeño con ROC-AUC de 0.9163, siendo una herramienta efectiva para la predicción de enfermedad cardíaca. La optimización
   de hiperparámetros mejoró todas las métricas, especialmente el recall, crucial para detectar casos positivos.

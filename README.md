Predicción de Enfermedad Cardíaca con XGBoost

  Descripción

  Análisis completo para predecir enfermedad cardíaca utilizando machine learning con XGBoost.

  Dataset

  - 920 pacientes de múltiples centros médicos
  - 13 variables clínicas (edad, sexo, presión arterial, colesterol, etc.)
  - Variable objetivo: Presencia de enfermedad cardíaca (binaria)

  Proceso

  1. Exploración: Análisis de estructura, valores faltantes y outliers
  2. EDA: Estadísticas descriptivas, correlaciones y visualizaciones
  3. Preprocesamiento: Limpieza de datos, imputación y escalado
  4. Modelado: XGBoost con optimización de hiperparámetros

  Resultados

  - F1-Score: 0.857
  - ROC-AUC: 0.916
  - Variables importantes: Frecuencia cardíaca máxima, dolor en pecho, edad

  Archivos

  - Heart_Disease_XGBoost_Completo.ipynb: Notebook con análisis completo
  - heart.csv: Dataset original

  Uso

  # Ejecutar notebook completo
  jupyter notebook Heart_Disease_XGBoost_Completo.ipynb

  Tecnologías

  Python, pandas, scikit-learn, XGBoost, matplotlib, seaborn

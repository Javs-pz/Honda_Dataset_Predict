Este proyecto lo hice para hacer una prediccion de acciones de Honda utilizando el modelo LSTM ya que fue el que mejor se adapto a esta base de datos. A continuacion voy a explicar como :

Optimizador: Adam.

Métricas: MAE, RMSE, o comparación visual

Explicación del código:

Normalización: Los datos se escalan a [0, 1] para mejorar la convergencia del modelo.

Secuencias: Cada ejemplo de entrenamiento es una ventana de 30 días (window_size), y la etiqueta es el precio del día siguiente.

Modelo LSTM:

Dos capas LSTM para capturar patrones complejos.

Dropout para reducir overfitting.

Métricas: Se calcula el RMSE (Root Mean Squared Error) para evaluar el error de predicción.

Visualización: Comparación gráfica entre precios reales y predichos.

Mejoras Clave Implementadas:
Bidirectional LSTM:

Capas Bidirectional analizan las secuencias en ambos sentidos (pasado → futuro y futuro → pasado), capturando patrones más complejos.

Early Stopping:

Detiene el entrenamiento si la pérdida en validación (val_loss) no mejora en 10 épocas (patience=10), evitando overfitting.

Múltiples Features:

Usamos Open, High, Low, Close, y Volume para enriquecer el modelo (en lugar de solo Close).

Ajuste de Hiperparámetros:

Aumento de neuronas (units=100).

Dropout más alto (0.3) para mayor regularización.

Learning rate personalizado (Adam(lr=0.001)).

Métricas Adicionales:

MAE (Mean Absolute Error): Para evaluar el error absoluto promedio.

Gráfico de pérdida: Visualiza cómo evoluciona el error durante el entrenamiento.

Resultados Esperados:
RMSE/MAE más bajos que el modelo anterior.

Curva de aprendizaje estable (sin overfitting gracias al Early Stopping y Dropout).

Predicciones más precisas gracias a las features adicionales y Bidirectional LSTM.

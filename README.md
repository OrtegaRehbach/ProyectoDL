# Evaluando el rendimiento de modelos de Machine Learning para Predicción de Enfermedades Cardíacas

Este proyecto utiliza técnicas de aprendizaje automático para predecir la presencia de enfermedades cardíacas en individuos con base en un conjunto de datos que contiene varios indicadores de salud.

## Descripción del Proyecto

El objetivo del proyecto es construir y comparar tres modelos de clasificación para predecir si una persona ha tenido un ataque al corazón. Se utilizan tres algoritmos de clasificación: Regresión Logística, Naive Bayes, y Random Forest, y se evalúan sus desempeños en términos de precisión (accuracy), puntuación F1, y tiempos de entrenamiento.

## Conjunto de Datos

El conjunto de datos utilizado proviene de Kaggle, específicamente de [Personal Key Indicators of Heart Disease](https://www.kaggle.com/datasets/kamilpytlak/personal-key-indicators-of-heart-disease/data), que incluye una serie de indicadores de salud:

- Estado de salud general (medido en días de salud física/mental)
- Hábitos de vida (horas de sueño, actividades físicas, consumo de cigarrillos)
- Historial médico (enfermedades crónicas como asma, diabetes, cáncer de piel)
- Datos demográficos (edad, sexo)
  
El objetivo (`HadHeartAttack_INT`) es una variable binaria donde `1` indica que la persona ha tenido un ataque al corazón y `0` indica que no.

## Estructura del Proyecto

- `data/`: Contiene el archivo `Heart_OnlyNum.csv` con los datos.
- `src/`: Contiene el notebook Jupyter con el código de análisis, entrenamiento, y evaluación de los modelos.
  
## Modelos Utilizados

Se implementaron tres algoritmos de clasificación:
1. **Regresión Logística**: Modelo lineal para clasificación binaria.
2. **Naive Bayes**: Clasificador probabilístico basado en la regla de Bayes.
3. **Random Forest**: Ensamble de árboles de decisión que mejora la precisión y generalización.

## Preprocesamiento

1. **Limpieza de datos**: Se eliminaron duplicados y columnas irrelevantes para mejorar el rendimiento.
2. **Estandarización**: Se estandarizaron las variables para mejorar el rendimiento de los modelos.
3. **Re-muestreo con SMOTE**: Se aplicó SMOTE para balancear las clases, dada la cantidad menor de ejemplos de ataque cardíaco.

## Entrenamiento y Evaluación

Cada modelo se entrenó en el conjunto de entrenamiento y se evaluó en el conjunto de prueba usando las siguientes métricas:
- **Exactitud (Accuracy)**
- **F1-Score**: Para ambas clases (`No Heart Disease` y `Heart Disease`)
- **Matriz de Confusión**: Visualización de predicciones correctas e incorrectas
- **Tiempo de Entrenamiento**

## Resultados

Las métricas de evaluación para cada modelo se visualizan en gráficos comparativos:
- **Precisión de cada modelo**: Comparación del desempeño general
- **F1-Score para ambas clases**: Comparación entre las clases de cada modelo
- **Tiempo de Entrenamiento**: Comparación de tiempos de entrenamiento para cada modelo

## Ejecución del Código

### Requisitos

Instalar los paquetes necesarios:
```bash
pip install -r requirements.txt
```

### Ejecución

Ejecuta el archivo principal en Jupyter Notebook para entrenar los modelos y generar las predicciones:
```bash
jupyter notebook notebooks/heart_disease_prediction.ipynb
```

## Ejemplo de Predicciones

Al final del análisis, se presentan predicciones de los primeros cinco ejemplos del conjunto de prueba. Cada modelo genera una predicción (`No Heart Disease` o `Heart Disease`), que se compara con la etiqueta real.
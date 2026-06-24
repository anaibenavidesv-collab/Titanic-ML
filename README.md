# Comparación de Modelos y Optimización de Pipeline en el Dataset Titanic

Trabajo de tutoría — **Introducción a Machine Learning** · Big Data · Ciclo VII
Facultad de Economía y Empresa — Carrera de Administración de Empresas (UCSG)

**Docente:** Ing. Xavier Jácome Piñeiros

## Integrantes
- Valentina Verónica Suárez De La Torre
- María Daniela Borbor Cabrera
- Anaí Betzabeth Benavides Vega
- Ricardo Alberto Zariquiey Salinas
- Christian Efren Cedeño Sotomayor

## Descripción
Problema de **clasificación binaria**: predecir si un pasajero del Titanic sobrevivió
(`Survived`: 0 = no, 1 = sí) a partir de sus características. El proyecto encapsula todo el
preprocesamiento en un **`Pipeline` de scikit-learn** (evita *data leakage*), compara **4 modelos**,
optimiza hiperparámetros con `GridSearchCV` y `RandomizedSearchCV` (`cv=5`), y analiza métricas,
overfitting e importancia de variables.

## Estructura del repositorio
| Archivo | Descripción |
|---|---|
| `titanic_clasificacion_ML_final.ipynb` | Notebook final, limpio y reproducible (la entrega). |
| `train.csv` | 891 pasajeros con etiqueta `Survived` (entrenamiento y validación). |
| `test.csv` | 418 pasajeros sin etiqueta (predicción final / simulación de producción). |
| `submission.csv` | Predicciones del mejor modelo sobre `test.csv` (formato Kaggle). |
| `Informe_Titanic.pdf` | Informe corto (máx. 4 páginas) con resultados y conclusiones. |
| `OBJETIVOS.md` | Enunciado oficial del profesor. |

## Cómo ejecutar

### Opción A — Google Colab (recomendada)
1. Abre `titanic_clasificacion_ML_final.ipynb` en [Google Colab](https://colab.research.google.com)
   (Archivo → Subir cuaderno).
2. Sube `train.csv` y `test.csv` al panel de archivos (icono de carpeta).
3. Entorno de ejecución → **Ejecutar todo**.

### Opción B — Local
```bash
pip install numpy pandas matplotlib seaborn scikit-learn
jupyter notebook titanic_clasificacion_ML_final.ipynb
```

## Reproducibilidad
Se fija `RANDOM_STATE = 42` en todo el flujo (split, modelos, validación cruzada y búsquedas),
por lo que el notebook produce **siempre los mismos resultados** al ejecutarse de arriba a abajo
("Restart & Run All").

## Resultados (resumen)
- **Mejor modelo:** Regresión Logística (F1 macro y AUC-ROC más altos en el holdout, y el menor overfitting).
- **Puntaje en Kaggle:** ~0.765 de accuracy sobre el `test.csv` real.

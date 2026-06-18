TRABAJO DE TUTORÍA — INTRODUCCIÓN A MACHINE LEARNING

Grupo: 4 estudiantes

Fecha de entrega: 23 de junio de 2025, 23h59

Modalidad de entrega: Un repositorio de GitHub por grupo con un notebook Jupyter limpio y ejecutable, más un informe corto en PDF o Markdown.



Título: Comparación de Modelos y Optimización de Pipeline en el Dataset Titanic

Contexto

En clases construimos un clasificador inicial sobre el dataset Titanic: imputamos valores faltantes básicos, codificamos variables categóricas y entrenamos un primer modelo. Posteriormente mejoramos el preprocesamiento con feature engineering (extracción del título del nombre, tamaño del grupo familiar, indicadores de cabina, etc.). Sin embargo, nos quedamos con un solo modelo y sin validar seriamente si ese modelo era el mejor posible.



Este trabajo les exige ir mucho más lejos: diseñar un pipeline completo, comparar múltiples algoritmos, optimizar hiperparámetros de forma sistemática, y analizar críticamente los resultados.



Objetivos

Implementar un pipeline de ML reproducible y bien estructurado.

Comparar al menos cuatro algoritmos de clasificación distintos bajo las mismas condiciones.

Aplicar búsqueda de hiperparámetros usando GridSearchCV o RandomizedSearchCV.

Evaluar los modelos con métricas más allá de la exactitud (accuracy): precisión, recall, F1-score, AUC-ROC.

Detectar y discutir el overfitting en los modelos entrenados.

Comunicar los resultados con visualizaciones claras y conclusiones fundamentadas.

Requisitos Técnicos

1\. Preprocesamiento y Feature Engineering (punto de partida: lo visto en clases)

Deben partir del feature engineering ya visto y agregar al menos dos nuevas variables que ellos mismos justifiquen. Ejemplos posibles (no obligatorios):



Fare\_per\_person: tarifa dividida para el tamaño del grupo.

Is\_alone: 1 si viajaba solo, 0 si no.

Interacciones entre variables (ej. Pclass \* Age).

Extracción de la cubierta del número de cabina.

Cada nueva variable debe ir acompañada de una justificación breve (2-3 oraciones): ¿por qué creen que aporta información predictiva?



2\. Pipeline con sklearn.pipeline.Pipeline

Todo el preprocesamiento (imputación, escalado, codificación) debe estar encapsulado en un Pipeline de scikit-learn. No se aceptan transformaciones manuales fuera del pipeline durante la etapa de entrenamiento/validación. Esto garantiza que no haya data leakage.



3\. Modelos a comparar

Deben entrenar y comparar al menos los siguientes cuatro modelos:



Árbol de Decisión (DecisionTreeClassifier)

Random Forest (RandomForestClassifier)

Gradient Boosting (GradientBoostingClassifier o XGBClassifier)

Un cuarto modelo a elección del grupo (ej. Regresión Logística, SVM, K-Nearest Neighbors, etc.) con justificación de su elección.

4\. Validación cruzada y búsqueda de hiperparámetros

Para al menos dos de los cuatro modelos, deben realizar una búsqueda de hiperparámetros usando GridSearchCV o RandomizedSearchCV con cv=5. Deben reportar:



Los hiperparámetros explorados y sus rangos.

Los mejores hiperparámetros encontrados.

La métrica usada para la selección (scoring), justificando por qué eligieron esa métrica y no otra.

5\. Evaluación comparativa

Para todos los modelos (con sus mejores hiperparámetros), deben presentar una tabla comparativa que incluya, sobre el conjunto de prueba:



Accuracy

Precision (macro)

Recall (macro)

F1-score (macro)

AUC-ROC

Adicionalmente, deben incluir:



La matriz de confusión del mejor modelo.

La curva ROC de todos los modelos en un mismo gráfico, con sus respectivos valores de AUC en la leyenda.

6\. Análisis de overfitting

Para cada modelo, deben reportar el score de entrenamiento y el score de validación cruzada. Luego deben responder en el informe: ¿Cuáles modelos muestran signos de overfitting? ¿Cómo lo mitigaron o cómo lo mitigarían?



7\. Importancia de variables

Para el mejor modelo obtenido, deben graficar las 10 variables más importantes (usando feature\_importances\_ si el modelo lo permite, o permutation\_importance como alternativa). Deben comentar si los resultados tienen sentido desde el punto de vista del dominio (el contexto histórico del Titanic).



Informe

Junto al notebook, deben entregar un informe de máximo 4 páginas (sin contar figuras) en formato PDF o Markdown que contenga:



Introducción (½ página): qué problema resuelven y qué van más allá de lo visto en clases.

Feature engineering aplicado (½ página): descripción y justificación de las nuevas variables.

Resultados (2 páginas): tabla comparativa, análisis de overfitting, gráficos principales con interpretación.

Conclusiones (1 página): ¿cuál modelo recomendarían y por qué? ¿Qué limitaciones tiene su análisis? ¿Qué harían si tuvieran más tiempo?

Distribución del Trabajo

El notebook debe incluir, en una celda Markdown al inicio, una tabla con el nombre de cada integrante y las tareas que realizó. Se evaluará que la distribución sea equitativa.


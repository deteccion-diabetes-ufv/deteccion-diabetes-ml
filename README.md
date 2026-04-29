# Detección Temprana de Diabetes — Machine Learning

Proyecto de clasificación supervisada para la detección precoz de diabetes tipo 2, desarrollado en Python.
Implementa y compara cuatro modelos de aprendizaje automático a partir de datos clínicos reales,
con el objetivo de identificar pacientes en riesgo de forma fiable.

---

## Resultados

Evaluado sobre el **Pima Indians Diabetes Dataset** (768 pacientes, 8 variables clínicas):

| Modelo | Accuracy | F1-score | AUC |
|---|---|---|---|
| Regresión Logística | 0.7273 | 0.63 | 0.8275 |
| Random Forest | 0.7532 | 0.67 | 0.8400 |
| SVM | 0.7338 | 0.64 | 0.7690 |
| Red Neuronal | 0.7468 | 0.64 | 0.8195 |

Random Forest obtuvo el mejor rendimiento global, con el AUC más alto (0.84) y mejor F1-score (0.67).

---

## Metodología

1. **Preprocesamiento**: los ceros en variables como glucosa o IMC son datos ausentes, no valores reales — se sustituyen por NaN y se imputan con la media
2. **Selección de variables**: correlación con la variable objetivo, umbral > 0.1
3. **Entrenamiento**: Regresión Logística, Random Forest, SVM y Red Neuronal (MLP)
4. **Optimización**: GridSearchCV con validación cruzada de 5 pliegues, métrica F1
5. **Evaluación**: matrices de confusión, curvas ROC y comparación de métricas entre modelos

---

## Requisitos

```
pandas
numpy
matplotlib
seaborn
scikit-learn
```

---

## Lecciones aprendidas

El preprocesamiento resultó ser el paso más crítico del proyecto. Un dataset aparentemente limpio
escondía valores imposibles desde el punto de vista clínico, detectarlo y tratarlo correctamente
marcó una diferencia real en el rendimiento de los modelos.

Se eligió F1-score como métrica de optimización frente al accuracy dado el desbalance de clases.
En un contexto médico, un falso negativo (paciente diabético no detectado) tiene consecuencias
mucho más graves que un falso positivo.

---

## Autores

- **Jorge Durbán Conejos**
- **Álvaro Hernández González**
- **Lucía Mateos Pérez**
- **Claudia Pedraza García**

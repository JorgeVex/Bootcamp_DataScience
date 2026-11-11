# Bootcamp en Data Science — Portafolio

**Jorge Hernán Velasco Gómez** · Ingeniería en Ciencia de Datos (Corporación Universitaria Iberoamericana)
Bootcamp en Data Science — Escuela BIT / IBERO · 300 horas · mayo – septiembre de 2026

Este repositorio reúne los entregables del bootcamp: fundamentos de Python, SQL, consumo de APIs con Power BI, aprendizaje no supervisado y un proyecto final de machine learning supervisado aplicado al sector salud.

---

## Proyecto final — Predicción de inasistencia a citas médicas (no-show)

📂 [`ProyectoFinal/`](ProyectoFinal/) · Python · pandas · scikit-learn · LightGBM

**Problema:** una de cada cinco citas médicas se pierde. El objetivo es estimar, con la información disponible al momento de asignar la cita, qué tan probable es que el paciente no asista, para que la IPS pueda priorizar a quién contactar.

**Datos:** [Medical Appointment No Shows](https://www.kaggle.com/datasets/joniarroba/noshowappointments) (Kaggle), 110.527 citas.

**Proceso**

1. EDA: limpieza de valores anómalos, tasa de inasistencia por variable y análisis del efecto aparente del SMS (que resultó ser un sesgo por días de espera).
2. Ingeniería de variables: días de espera, historial de inasistencia del paciente, franja de edad, día y hora de asignación.
3. Modelado con validación cruzada estratificada y búsqueda de hiperparámetros: Regresión Logística, Random Forest y LightGBM.
4. Evaluación con ROC-AUC, PR-AUC, sobreajuste, importancia por permutación y ajuste del umbral.

**Resultados**

| Métrica | LightGBM (modelo final) |
| --- | --- |
| ROC-AUC (prueba) | 0,741 |
| PR-AUC (prueba) | 0,385 (casi el doble del azar) |
| No-show en el 10 % de citas de mayor riesgo | 43,7 % |
| No-show en el 10 % de citas de menor riesgo | 2,2 % |

- Los **días de espera** son el factor principal: las citas del mismo día casi no se pierden (4,7 %), y desde el primer día de espera la tasa sube a cerca del 23 %.
- **Uso práctico:** si la IPS solo puede llamar al 20 % de las citas, escogerlas con el modelo cubre el 38,8 % de los no-shows, casi el doble que hacerlo al azar.

---

## Talleres

| Carpeta | Tema | Qué se hizo | Herramientas |
| --- | --- | --- | --- |
| [`Taller05/`](Taller05/) | Clustering de canciones de Spotify | Segmentación de 1.000 canciones por sus características de audio: estandarización, PCA, K-Means (k elegido con codo y silueta) y comparación con DBSCAN. Interpretación de 4 perfiles musicales. | scikit-learn, pandas, seaborn |
| [`Taller04/`](Taller04/) | API + Power BI | Consulta del clima de varias ciudades a la API de Open-Meteo, transformación de JSON a DataFrame, limpieza, exportación a CSV y dashboard interactivo en Power BI. | requests, pandas, Power BI |
| [`TallerSQL/`](TallerSQL/) | SQL sobre Sakila | 13 ejercicios en MySQL: filtros, ordenamiento, JOINs, INSERT / UPDATE / DELETE y consultas avanzadas. | MySQL |
| [`Actividad1.ipynb`](Actividad1.ipynb) | Python básico | Captura y validación de datos, estructuras de datos, reglas de negocio con condicionales y ciclos, funciones y manejo de errores. | Python |

---

## Cómo ejecutar

```bash
git clone https://github.com/JorgeVex/Bootcamp_DataScience
pip install pandas numpy matplotlib seaborn scikit-learn lightgbm requests
```

Cada notebook se abre en Jupyter o Google Colab. Los datasets están dentro de la carpeta de cada proyecto. El archivo `.pbix` del Taller04 se abre con Power BI Desktop.

---

## Contacto

[LinkedIn](https://linkedin.com/in/jorge-hernán-velasco-gomez-776b39266) · [GitHub](https://github.com/JorgeVex)

# 📊 Predicción de Llamadas Entrantes de Cabinas de Telepresencia con Machine Learning

Este repositorio contiene el desarrollo de un modelo predictivo para anticipar el volumen de llamadas entrantes desde **cabinas de telepresencia** en centros de atención al cliente de una empresa de telecomunicaciones en Perú. Se utilizaron técnicas de aprendizaje automático supervisado aplicadas a datos correspondientes del periodo **abril 2024 - abril 2025**.

---

## 🎯 Objetivo del Proyecto

Predecir el número de llamadas entrantes desde cabinas de telepresencia ubicadas en centros de atención al cliente de una empresa de telecomunicaciones basado en las llamadas del 2024 y 2025 utilizando modelos de aprendizaje automático.

---

## 🧠 Modelos de Machine Learning Utilizados

Se evaluaron varios modelos de regresión:

- ✅ **Random Forest**
- ✅ **Gradient Boosting Regressor (GBR)**
- ✅ **XGBoost**
- ✅ **LightGBM (LGBM)** — *Mejor desempeño*

> Se aplicó la metodología **CRISP-DM** para un proceso estructurado y reproducible.

---

## 📈 Principales Resultados

| Modelo       | R² Score | RMSE   | MAE    |
|--------------|----------|--------|--------|
| LightGBM     | 0.9985   | 0.1250 | 0.0283 |
| XGBoost      | 0.7111   | 2.0783 | 1.4451 |
| GBR          | 0.7132   | 2.0708 | 1.4409 |
| Random Forest| 0.9960   | 0.2059 | 0.0264 |

> El modelo LightGBM fue el más preciso, permitiendo predicciones confiables por rango horario.

---

## 🧰 Herramientas y Tecnologías

- Python 3.x
- Scikit-learn
- LightGBM
- XGBoost
- Pandas / NumPy
- Seaborn / Matplotlib
- BorutaPy (para selección de variables)

---

## 📁 Estructura del Repositorio

├── data/
│ └── llamadas_telepresencia.csv # Dataset base (anonimizado o de ejemplo)
├── notebooks/
│ └── modelado_LightGBM.ipynb # Notebook principal
│ └── analisis_exploratorio.ipynb # Análisis exploratorio y EDA
├── resultados/
│ └── metricas_modelos.csv # Comparación de modelos
├── utils/
│ └── funciones_preprocesamiento.py
├── README.md

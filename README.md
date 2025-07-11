# 📊 Predicción de Llamadas Entrantes en Cabinas de Telepresencia con Machine Learning

Este repositorio contiene el desarrollo de un modelo predictivo para anticipar el volumen de llamadas entrantes desde **cabinas de telepresencia** en centros de atención al cliente de una empresa de telecomunicaciones en Perú. Se utilizaron técnicas de aprendizaje automático supervisado aplicadas a datos reales del período **abril 2024 - abril 2025**.

---

## 🎯 Objetivo del Proyecto

Predecir la cantidad de llamadas entrantes por rango horario desde cabinas de telepresencia, con el fin de:

- Optimizar la asignación de agentes de atención.
- Mejorar la eficiencia operativa.
- Reducir los tiempos de espera.
- Elevar la satisfacción del cliente.

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
| XGBoost      | ...      | ...    | ...    |
| GBR          | ...      | ...    | ...    |
| Random Forest| ...      | ...    | ...    |

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


# 📊 APLICACIÓN DE APRENDIZAJE AUTOMÁTICO PARA EL PRONÓSTICO DE LLAMADAS ENTRANTES DESDE CABINAS DE TELEPRESENCIA 

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


## 📌 Variables Consideradas
- Temporales: Año, mes, día, semana, feriado, fin de semana, rango horario, día laboral, estación, semana2, semana3.
- Geográficas: Oficina, región,canal.
- Atención: Tipo de atención, promedios históricos.

---

## 🔢 Protocolo de experimentación

Se evaluaron 4 modelos bajo un protocolo de experimentación.

### Detalle de Hiperparámetros y Experimentaciones

#### Random Forest
| Hiperparámetro            | Valores                       | Nº Experimentos |
|---------------------------|-------------------------------|-----------------|
| Número de árboles         | 20, 30, 50, 100               | 4               |
| Max Features              | 0.01, 0.1, 0.3, 0.5, 1        | 5               |
| Nº muestras por nodo      | 6, 7, 8, 9, 10                | 5               |
| **Total de experimentaciones** |                               | **100**         |

#### XGBoost
| Hiperparámetro            | Valores                       | Nº Experimentos |
|---------------------------|-------------------------------|-----------------|
| Profundidad máxima        | 3, 5, 7, 9                    | 4               |
| Tasa de aprendizaje       | 0.01, 0.001, 0.0001           | 3               |
| Subsample                 | 0.8, 0.9, 1                   | 3               |
| Nº de iteraciones         | 1000                          | 1               |
| Nº de núcleos             | 2                             | 1               |
| Función de pérdida        | reg:squarederror              | 1               |
| Lambda                    | 1, 2                          | 2               |
| Alpha                     | 0, 0.5                        | 2               |
| **Total de experimentaciones** |                               | **144**         |

#### Gradient Boosting Regressor
| Hiperparámetro            | Valores                       | Nº Experimentos |
|---------------------------|-------------------------------|-----------------|
| Número de árboles         | 100, 300, 500                 | 3               |
| Tasa de aprendizaje       | 0.001, 0.01, 0.05             | 3               |
| Profundidad de árbol      | 3, 5, 7, 9                    | 4               |
| Min_samples_split         | 10                            | 1               |
| Min_samples_leaf          | 5                             | 1               |
| Subsample                 | 0.8, 1                        | 2               |
| max_features              | 0.8, 1                        | 2               |
| **Total de experimentaciones** |                               | **144**         |

#### LightGBM
| Hiperparámetro                    | Valores                       | Nº Experimentos |
|-----------------------------------|-------------------------------|-----------------|
| Número de árboles                 | 100, 300, 500                 | 3               |
| Número máximo de hojas            | 31, 50                        | 2               |
| Tasa de aprendizaje               | 0.01, 0.05, 0.1               | 3               |
| Profundidad de árbol              | -1, 5, 10                     | 3               |
| Mínimo número de muestras por hoja| 1, 20                         | 2               |
| Objective                         | regression                    | 1               |
| Tipo de boosting                  | gbdt                          | 1               |
| **Total de experimentaciones**     |                               | **108**         |

> **Total general de experimentaciones: 496**
---

## 📈 Principales Resultados (Test)

| Modelo        | R² Score | RMSE   | MAE    | MAPE (%) |
|---------------|----------|--------|--------|----------|
| LightGBM      | 0.9985   | 0.1250 | 0.0283 | 0.5345   |
| XGBoost       | 0.7111   | 2.0783 | 1.4451 | 51.0218  |
| GBR           | 0.7132   | 2.0708 | 1.4409 | 50.7703  |
| Random Forest | 0.9960   | 0.2059 | 0.0264 | 0.5388   |

 El modelo LightGBM fue el más preciso, permitiendo predicciones confiables por rango horario. Los hiperparámetros del modelo de LGBM fueron:
- n_estimators: 500
- num_leaves:	50
- learning_rate:	0.1
- max_depth:	-1
- min_child_samples:	20
- objective:	regression
- boosting_type:	gbdt


---

## 🧰 Herramientas y Tecnologías

- Python 3.x
- Scikit-learn
- LightGBM
- XGBoost
- Pandas / NumPy
- Seaborn / Matplotlib




---
## 📌 Conclusiones

Los modelos de aprendizaje automático lograron predecir el número de llamadas entrantes desde cabinas de telepresencia ubicadas en centros de atención al cliente de una empresa de telecomunicaciones basado en las llamadas del 2024 y 2025.

La exploración y preparación del conjunto de datos históricos de llamadas entrantes del 2024 y 2025 contribuyeron a la predicción del número de llamadas entrantes desde cabinas de telepresencia ya que proporcionan datos procesados y listos para usar en modelos de machine learning. 

La aplicación de los modelos Random Forest, XGBoost, GBR y LGBM contribuyeron a la predicción del número de llamadas entrantes desde cabinas de telepresencia ya que brindan diferentes predicciones para una posterior comparación.

El modelo LightGBM tuvo los mejores resultados R^2  y RMSE en la predicción del número de llamadas entrantes desde cabinas de telepresencia.

---
## 📌 Recomendaciones

Adicionar más variables derivadas (engineered features) y evaluar si mejora el resultado de los indicadores ya que, aunque el modelo ha demostrado una capacidad predictiva sobresaliente, es recomendable continuar explorando y creando variables derivadas que puedan capturar patrones más profundos en los datos.

Adicionar variables externas y evaluar el impacto que tendrían en el desempeño del modelo debido a que actualmente, el modelo se basa en variables internas del sistema (día, canal, tipo de atención, etc.), pero se sugiere incluir variables externas que puedan afectar la demanda de llamadas y que no están contenidas en el sistema, como condiciones climáticas, eventos relevantes, cortes de servicio previos o mantenimiento, etc.

Evaluar modelos adicionales encontrados en el estado del arte como GRU y SARIMA pues si bien los modelos basados en árboles (LightGBM, XGBoost, Random Forest) han ofrecido excelentes resultados, es importante contrastarlos con enfoques alternativos, especialmente aquellos orientados a series temporales.

Ampliar el periodo de recolección de datos dado que el dataset cubre un año (abril 2024 - abril 2025), se recomienda extender la cobertura a múltiples años para identificar patrones multianuales, efectos post-pandemia o cambios por estacionalidades específicas.

Una vez implementado, el modelo debe ser monitoreado mensualmente. Si la demanda cambia, el modelo debe reentrenarse.


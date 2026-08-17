<a id="english-version"></a>

# Airport Taxi Demand Forecasting 🚕

[Go to Spanish version](#spanish-version)

Time series forecasting of hourly airport taxi demand using feature engineering and machine learning to support driver allocation and peak-hour planning.

---

### Business context

Sweet Lift Taxi needs to anticipate airport ride demand to improve driver availability during peak periods. Reliable short-term forecasts can support capacity planning, reduce passenger waiting times, and improve the allocation of operational resources.

### Analytical objective

Develop and evaluate time series models that predict the number of taxi orders for the next hour using historical demand patterns.

The evaluation metric is Root Mean Squared Error (RMSE), with a target of no more than 48 orders per hour on the test set.

### Data

The analysis uses historical taxi order records collected at 10-minute intervals from March through August 2018.

- Original observations: 26,496
- Hourly observations after resampling: 4,416
- Target variable: `num_orders`
- Time index: `datetime`

The source dataset is not included in this repository.

### Analytical workflow

1. Chronological validation and initial data quality review.
2. Hourly resampling by summing taxi orders.
3. Trend and daily seasonality analysis.
4. Feature engineering using calendar variables, 24 hourly lags, and a shifted 24-hour rolling mean.
5. Chronological split using the most recent 10% of observations as the test set.
6. Training and comparison of Linear Regression, Decision Tree, and Random Forest models.
7. Final evaluation using RMSE.

### Model performance

| Model | Training RMSE | Test RMSE |
|---|---:|---:|
| Linear Regression | 25.74 | 45.73 |
| Decision Tree | 15.57 | 60.95 |
| Random Forest | 14.22 | **44.40** |

Random Forest achieved the best test performance with an RMSE of 44.40, meeting the defined threshold of 48 orders per hour.

### Business relevance

The results provide an analytical basis for evaluating short-term decisions related to driver availability and coverage during high-demand periods. Before operational use, the model should be validated across multiple time windows, compared with a simple baseline, monitored for performance drift, and updated as demand behavior changes.

### Technologies

- Python
- pandas
- Matplotlib
- seaborn
- statsmodels
- scikit-learn
- Jupyter Notebook

### Repository structure

```text
airport_taxi_demand_forecasting/
├── taxi_demand_forecasting_model.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

---

<a id="spanish-version"></a>

# Pronóstico de demanda de taxis en aeropuertos 🚕

[Ir a la versión en inglés](#english-version)

### Contexto de negocio

Sweet Lift Taxi necesita anticipar la demanda de viajes en aeropuertos para mejorar la disponibilidad de conductores durante los períodos de mayor actividad. Los pronósticos de corto plazo pueden respaldar la planificación de capacidad, reducir los tiempos de espera y mejorar la asignación de recursos operativos.

### Objetivo analítico

Desarrollar y evaluar modelos de series temporales que permitan predecir el número de pedidos de taxi para la siguiente hora a partir del comportamiento histórico de la demanda.

La métrica de evaluación es la raíz del error cuadrático medio (RMSE), con un límite máximo de 48 pedidos por hora en el conjunto de prueba.

### Datos

El análisis utiliza registros históricos de pedidos de taxi recopilados en intervalos de diez minutos entre marzo y agosto de 2018.

- Observaciones originales: 26,496
- Observaciones horarias después del remuestreo: 4,416
- Variable objetivo: `num_orders`
- Índice temporal: `datetime`

El dataset original no está incluido en este repositorio.

### Flujo analítico

1. Validación cronológica y revisión inicial de calidad de los datos.
2. Remuestreo horario mediante la suma de pedidos.
3. Análisis de tendencia y estacionalidad diaria.
4. Ingeniería de variables mediante atributos de calendario, 24 rezagos horarios y un promedio móvil desplazado de 24 horas.
5. División cronológica, reservando el 10 % más reciente de las observaciones para prueba.
6. Entrenamiento y comparación de Regresión Lineal, Árbol de Decisión y Random Forest.
7. Evaluación final mediante RMSE.

### Desempeño de los modelos

| Modelo | RMSE de entrenamiento | RMSE de prueba |
|---|---:|---:|
| Regresión Lineal | 25.74 | 45.73 |
| Árbol de Decisión | 15.57 | 60.95 |
| Random Forest | 14.22 | **44.40** |

Random Forest obtuvo el mejor desempeño en el conjunto de prueba con un RMSE de 44.40, resultado inferior al límite establecido de 48 pedidos por hora.

### Relevancia para el negocio

Los resultados aportan una base analítica para evaluar decisiones de corto plazo relacionadas con disponibilidad de conductores y cobertura durante períodos de alta demanda. Antes de utilizar el modelo en un entorno operativo, es necesario validarlo en múltiples períodos temporales, compararlo con una referencia simple, monitorear cambios en su desempeño y actualizarlo cuando cambie el comportamiento de la demanda.

### Tecnologías

- Python
- pandas
- Matplotlib
- seaborn
- statsmodels
- scikit-learn
- Jupyter Notebook

### Estructura del repositorio

```text
airport_taxi_demand_forecasting/
├── taxi_demand_forecasting_model.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

## Author / Autora

Carolina Caycho
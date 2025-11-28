# 🌾 RiceYield AI: Predicción de Rendimiento Agrícola Para Pequeños Productores

> 🏆 **Premio al Mejor Póster de Pregrado** - 4to Congreso "Vive la Investigación" (UTEM).
> Proyecto seleccionado entre +99 trabajos de investigación.

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-LightGBM%20%7C%20MLP-orange)
![Data Engineering](https://img.shields.io/badge/Data%20Eng-NASA%20%26%20WoSIS%20APIs-green)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📄 Descripción del Proyecto

Este proyecto aborda el desafío de la seguridad alimentaria en la India mediante el desarrollo de modelos de Inteligencia Artificial para predecir el rendimiento de cultivos de arroz (*Yield*). 

A diferencia de los enfoques tradicionales que utilizan datasets estáticos, este proyecto implementó un pipeline de **enriquecimiento de datos geoespaciales**, integrando variables climáticas históricas y propiedades químicas del suelo en tiempo de ejecución.

El estudio compara el desempeño de Redes Neuronales (Perceptrón Multicapa) frente a algoritmos de Gradient Boosting (LightGBM, XGBoost, CatBoost), demostrando la eficacia de los ensambles de árboles en datos tabulares agrícolas.

## 🚀 Características Clave (Ingeniería de Datos)

El valor principal de este proyecto reside en la construcción del dataset:

* **🌐 Integración API NASA POWER:** Extracción automática de datos meteorológicos históricos (precipitación, temperatura, radiación) alineados con las coordenadas (Lat/Lon) y las temporadas de cultivo (Kharif, Rabi, etc.).
* **asd Integración API WoSIS (ISRIC):** Obtención de datos edafológicos granulares. Se parsearon respuestas JSON complejas para extraer:
    * Nitrógeno, Fósforo, Potasio (NPK).
    * pH y Carbono Orgánico del suelo.
    * Humedad (con imputación basada en rangos de literatura científica).
* **⚡ Sistema de Caché Inteligente:** Implementación de almacenamiento local (`soil_cache.json`, `climate_cache.json`) para optimizar llamadas a APIs y reducir tiempos de re-entrenamiento.

## 📊 Resultados y Modelado

Se evaluaron múltiples arquitecturas. A pesar de diseñar un **MLP (Multi-Layer Perceptron)** robusto, los resultados empíricos favorecieron a los modelos de Boosting, lo cual es consistente con la literatura para datos tabulares de tamaño medio.

| Modelo | R² Score | Observaciones |
| :--- | :--- | :--- |
| **LightGBM** | **0.552** | Mejor balance general y velocidad. |
| **CatBoost** | 0.548 | Muy cercano al mejor desempeño. |
| **Random Forest** | 0.534 | Robusto pero más lento en inferencia. |
| **MLP (Red Neuronal)** | 0.228 | Dificultad para capturar relaciones no lineales complejas con estos datos específicos. |

> **Conclusión Técnica:** Las variables de manejo agronómico (uso de fertilizantes y pesticidas) resultaron ser los predictores más fuertes, seguidos por las variables climáticas derivadas de la API.

## 📂 Estructura del Repositorio

El proyecto sigue una estructura de directorios orientada a la reproducibilidad:

```text
RiceYield-AI-Prediction/
├── data/
│   ├── raw/              # Dataset base (crop_yield.csv) y geográficos
│   ├── processed/        # Datos limpios y enriquecidos listos para ML
│   └── cache/            # Respuestas JSON cacheadas de NASA/WoSIS
├── models/               # Modelos serializados (.pkl) y Scalers
├── docs/                 # Informe Técnico y Póster ganador (PDFs)
└── RICE_YIELD_AI.ipynb   # Notebook principal: ETL, EDA y Entrenamiento
¡Manos a la obra! Este README.md será la cara visible de tu trabajo ante los investigadores e ingenieros del CENIA. Debe ser técnico, claro y visualmente atractivo.

He redactado una versión profesional basada en tu informe y el póster. Destaca la Ingeniería de Datos (las APIs) y la honestidad científica (comparación de modelos), dos cosas que valoran mucho.

Copia y pega el siguiente código Markdown en tu archivo README.md.

Markdown

# 🌾 RiceYield AI: Predicción de Rendimiento Agrícola en India

> 🏆 **Premio al Mejor Póster de Pregrado** - 4to Congreso "Vive la Investigación" (UTEM).
> Proyecto seleccionado entre +99 trabajos de investigación.

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-LightGBM%20%7C%20MLP-orange)
![Data Engineering](https://img.shields.io/badge/Data%20Eng-NASA%20%26%20WoSIS%20APIs-green)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📄 Descripción del Proyecto

Este proyecto aborda el desafío de la seguridad alimentaria en la India mediante el desarrollo de modelos de Inteligencia Artificial para predecir el rendimiento de cultivos de arroz (*Yield*). 

A diferencia de los enfoques tradicionales que utilizan datasets estáticos, este proyecto implementó un pipeline de **enriquecimiento de datos geoespaciales**, integrando variables climáticas históricas y propiedades químicas del suelo en tiempo de ejecución.

El estudio compara el desempeño de Redes Neuronales (Perceptrón Multicapa) frente a algoritmos de Gradient Boosting (LightGBM, XGBoost, CatBoost), demostrando la eficacia de los ensambles de árboles en datos tabulares agrícolas.

## 🚀 Características Clave (Ingeniería de Datos)

El valor principal de este proyecto reside en la construcción del dataset:

* **🌐 Integración API NASA POWER:** Extracción automática de datos meteorológicos históricos (precipitación, temperatura, radiación) alineados con las coordenadas (Lat/Lon) y las temporadas de cultivo (Kharif, Rabi, etc.).
* **asd Integración API WoSIS (ISRIC):** Obtención de datos edafológicos granulares. Se parsearon respuestas JSON complejas para extraer:
    * Nitrógeno, Fósforo, Potasio (NPK).
    * pH y Carbono Orgánico del suelo.
    * Humedad (con imputación basada en rangos de literatura científica).
* **⚡ Sistema de Caché Inteligente:** Implementación de almacenamiento local (`soil_cache.json`, `climate_cache.json`) para optimizar llamadas a APIs y reducir tiempos de re-entrenamiento.

## 📊 Resultados y Modelado

Se evaluaron múltiples arquitecturas. A pesar de diseñar un **MLP (Multi-Layer Perceptron)** robusto, los resultados empíricos favorecieron a los modelos de Boosting, lo cual es consistente con la literatura para datos tabulares de tamaño medio.

| Modelo | R² Score | Observaciones |
| :--- | :--- | :--- |
| **LightGBM** | **0.552** | Mejor balance general y velocidad. |
| **CatBoost** | 0.548 | Muy cercano al mejor desempeño. |
| **Random Forest** | 0.534 | Robusto pero más lento en inferencia. |
| **MLP (Red Neuronal)** | 0.228 | Dificultad para capturar relaciones no lineales complejas con estos datos específicos. |

> **Conclusión Técnica:** Las variables de manejo agronómico (uso de fertilizantes y pesticidas) resultaron ser los predictores más fuertes, seguidos por las variables climáticas derivadas de la API.

## 📂 Estructura del Repositorio

El proyecto sigue una estructura de directorios orientada a la reproducibilidad:

```text
RiceYield-AI-Prediction/
├── data/
│   ├── raw/              # Dataset base (crop_yield.csv) y geográficos
│   ├── processed/        # Datos limpios y enriquecidos listos para ML
│   └── cache/            # Respuestas JSON cacheadas de NASA/WoSIS
├── models/               # Modelos serializados (.pkl) y Scalers
├── docs/                 # Informe Técnico y Póster ganador (PDFs)
└── RICE_YIELD_AI.ipynb   # Notebook principal: ETL, EDA y Entrenamiento
## 🛠️ Tecnologías Utilizadas
Lenguaje: Python 🐍

Data Processing: Pandas, NumPy.

Machine Learning: Scikit-Learn, LightGBM, XGBoost, CatBoost.

Visualización: Matplotlib, Seaborn.

APIs: requests para consumo de servicios REST geoespaciales.

## 👥 Autores y Créditos
Este trabajo fue desarrollado como parte del Laboratorio de Inteligencia Artificial en la Universidad Tecnológica Metropolitana (UTEM).

[Patricio Abarca Hernández] - [https://github.com/Begluckt]

[Rodrigo Tapia Ferrada] - [https://github.com/Chucaflu11]

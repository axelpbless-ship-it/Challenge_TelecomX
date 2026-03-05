# 📡 Challenge 2 Data Science — TelecomX Latam

Análisis de evasión de clientes (Churn) de la empresa TelecomX aplicando el proceso completo de ETL y Análisis Exploratorio de Datos (EDA), con el objetivo de identificar patrones y factores de riesgo que orienten estrategias de retención.

---

## 📋 Descripción del Proyecto

Este proyecto forma parte del **Challenge 2 de Data Science de Alura Latam**. A partir de datos extraídos desde una API en formato JSON, se realiza todo el proceso de Extracción, Transformación y Carga (ETL), seguido de un análisis exploratorio con visualizaciones estratégicas y un informe final con conclusiones y recomendaciones.

---

## 🎯 Objetivos

- Extraer datos desde una API en formato JSON usando Python
- Aplicar el proceso **ETL** completo: limpieza, transformación y carga
- Crear visualizaciones para identificar patrones de evasión
- Realizar un **Análisis Exploratorio de Datos (EDA)**
- Generar un informe con insights y recomendaciones estratégicas

---

## 📁 Estructura del Proyecto

```
challenge-telecomx/
│
├── TelecomX_LATAM.ipynb     # Notebook principal con el análisis completo
└── README.md                # Este archivo
```

---

## 🗂️ Estructura del Notebook

El notebook está organizado en 4 secciones:

### 🔴 Extracción
- Carga de datos desde la API oficial en formato JSON
- Exploración inicial: dimensiones, tipos de datos, nulos y duplicados
- Consulta del diccionario de datos e identificación de columnas relevantes

### 🔧 Transformación
- Normalización de columnas anidadas con `pd.json_normalize()`
- Limpieza: conversión de tipos, eliminación de nulos e imputación con mediana
- Creación de la columna `Cuentas_Diarias` (Cargo Mensual / 30)
- Estandarización: renombrado al español y codificación binaria (Yes→1, No→0)

### 📊 Carga y Análisis
- Estadísticas descriptivas (media, mediana, desviación estándar)
- 7 visualizaciones estratégicas para análisis de evasión

### 📝 Informe Final
- Resumen ejecutivo con métricas calculadas dinámicamente
- Conclusiones e insights basados en los datos
- Recomendaciones estratégicas para reducir la evasión

---

## 📊 Visualizaciones Incluidas

| # | Gráfico | Tipo | Descripción |
|---|---------|------|-------------|
| 1 | Distribución de Evasión | Barras + Pie | Proporción de clientes que se fueron vs. permanecen |
| 2 | Evasión por Variables Categóricas | Barras múltiples | Género, contrato, método de pago, internet, etc. |
| 3 | Variables Numéricas por Evasión | Histogramas | Meses, cargo mensual, cargo total, cuentas diarias |
| 4 | Cargo Mensual por Contrato | Boxplot | Comparativa por tipo de contrato y evasión |
| 5 | Servicios Adicionales vs Evasión | Barras múltiples | Seguridad, soporte, streaming, respaldo, etc. |
| 6 | Evasión por Antigüedad | Línea + área | Tasa de abandono según meses de contrato |
| 7 | Mapa de Correlaciones | Heatmap | Correlación entre todas las variables numéricas |

---

## 🛠️ Tecnologías Utilizadas

| Librería | Uso |
|----------|-----|
| `pandas` | Carga, limpieza y transformación de datos |
| `numpy` | Operaciones numéricas auxiliares |
| `matplotlib` | Visualizaciones principales |
| `seaborn` | Boxplot y mapa de calor |
| `requests` | Extracción de datos desde la API JSON |

---

## ▶️ Cómo Ejecutar

1. Abre el archivo `TelecomX_LATAM.ipynb` en [Google Colab](https://colab.research.google.com/)
2. Ejecuta las celdas en orden (Entorno de ejecución → Ejecutar todo)
3. No es necesario instalar dependencias adicionales, todas las librerías están disponibles en Colab por defecto

---

## 🗃️ Fuente de Datos

Los datos fueron provistos por Alura Latam y se cargan directamente desde su repositorio oficial:

```
https://raw.githubusercontent.com/alura-cursos/challenge2-data-science-LATAM/main/TelecomX_Data.json
```

### 📖 Diccionario de Datos

| Campo | Descripción |
|-------|-------------|
| `customerID` | Número de identificación único de cada cliente |
| `Churn` | Si el cliente dejó o no la empresa |
| `gender` | Género del cliente (Male / Female) |
| `SeniorCitizen` | Si el cliente tiene 65 años o más (1=Sí, 0=No) |
| `Partner` | Si el cliente tiene pareja (Yes / No) |
| `Dependents` | Si el cliente tiene dependientes (Yes / No) |
| `tenure` | Meses que lleva el cliente con la empresa |
| `PhoneService` | Suscripción al servicio telefónico |
| `MultipleLines` | Suscripción a más de una línea telefónica |
| `InternetService` | Proveedor de internet contratado |
| `OnlineSecurity` | Suscripción adicional de seguridad en línea |
| `OnlineBackup` | Suscripción adicional de respaldo en línea |
| `DeviceProtection` | Suscripción adicional de protección del dispositivo |
| `TechSupport` | Soporte técnico con menor tiempo de espera |
| `StreamingTV` | Suscripción de televisión por cable |
| `StreamingMovies` | Suscripción de streaming de películas |
| `Contract` | Tipo de contrato (mes a mes, anual, bianual) |
| `PaperlessBilling` | Si el cliente prefiere factura en línea |
| `PaymentMethod` | Forma de pago |
| `Charges.Monthly` | Total de todos los servicios del cliente por mes |
| `Charges.Total` | Total gastado por el cliente durante su permanencia |

---

## 📝 Principales Hallazgos

- Los clientes con **contratos mes a mes** presentan la mayor tasa de abandono
- Los **primeros meses** de contrato son el período más crítico de retención
- Los **cargos mensuales elevados** están correlacionados con mayor evasión
- Clientes **sin soporte técnico ni seguridad online** evaden con más frecuencia
- Los **adultos mayores** muestran una tasa de evasión más elevada que el promedio

---

## 👤 Autor

Desarrollado como parte del programa de formación en Data Science de **Alura Latam**.

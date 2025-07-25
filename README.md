# 📊 Análisis de Evasión (Churn) de Clientes en TelecomX

## 🎯 Propósito del Análisis

El presente proyecto se enfoca en el análisis de la **evasión de clientes (Churn)** en la empresa de telecomunicaciones **TelecomX**. El churn representa un desafío crítico para las empresas del sector, ya que la retención de clientes es fundamental para la sostenibilidad y el crecimiento.

El objetivo principal de este análisis es:
* **Identificar los factores clave** que influyen en la decisión de los clientes de darse de baja del servicio.
* **Comprender patrones y características** comunes entre los clientes que abandonan la empresa.
* **Proveer insights accionables** que permitan a TelecomX desarrollar estrategias de retención más efectivas y proactivas.

A través de la limpieza de datos, el análisis exploratorio (EDA) y la visualización, buscamos transformar los datos crudos en conocimiento valioso para la toma de decisiones estratégicas.

## 📁 Estructura del Proyecto y Organización de Archivos

El proyecto está organizado en un único notebook Colab, que contiene todos los pasos del análisis de principio a fin.

* `TelecomX_LATAM.ipynb`: Es el archivo principal del proyecto. Contiene todo el código Python para la importación, limpieza, preprocesamiento, análisis exploratorio de datos, generación de gráficos, y las conclusiones y recomendaciones.
* **Datos:** Los datos se obtienen directamente de una URL pública (`https://raw.githubusercontent.com/ingridcristh/challenge2-data-science-LATAM/refs/heads/main/TelecomX_Data.json`), por lo que no es necesario descargar un archivo de datos por separado.

## 📈 Ejemplos de Gráficos e Insights Obtenidos

Durante el análisis exploratorio de datos, se generaron diversas visualizaciones que revelaron patrones significativos:

### **1. Distribución del Churn**
Se visualizó la proporción de clientes que permanecen y los que se dan de baja.
* **Insight:** Aproximadamente el **26.54%** de los clientes de TelecomX hacen churn, lo que indica un problema de desbalance de clases a considerar para el modelado.
    *(Ver gráficos de barras y de torta para la variable 'Churn' en el notebook)*

### **2. Antigüedad del Cliente (`customer.tenure`) vs. Churn**
* **Insight:** La **baja antigüedad** (especialmente en los primeros meses) está fuertemente correlacionada con una **alta tasa de churn**. Los clientes nuevos son más propensos a irse.
    *(Ver histograma y boxplot de 'customer.tenure' vs 'Churn' en el notebook)*

### **3. Tipo de Contrato (`account.Contract`) vs. Churn**
* **Insight:** Los clientes con contratos **"Month-to-month"** (mes a mes) tienen una tasa de churn significativamente más alta (alrededor del 42%) en comparación con contratos de "One year" o "Two year" (que son muy bajos).
    *(Ver countplot de 'account.Contract' con 'Churn' y barra de porcentajes en el notebook)*

### **4. Servicio de Internet (`internet.InternetService`) vs. Churn**
* **Insight:** Los clientes con servicio de **"Fiber optic"** (Fibra Óptica) presentan una tasa de churn más elevada, lo que sugiere posibles problemas de satisfacción o manejo de expectativas con este servicio.
    *(Ver countplot de 'internet.InternetService' con 'Churn' en el notebook)*

### **5. Método de Pago (`account.PaymentMethod`) vs. Churn**
* **Insight:** El uso de **"Electronic check"** (cheque electrónico) como método de pago está asociado a una tasa de churn notablemente más alta.
    *(Ver countplot de 'account.PaymentMethod' con 'Churn' en el notebook)*

### **6. Correlación y Servicios Adicionales**
Se realizó una matriz de correlación para entender la relación entre todas las variables numéricas (incluyendo las codificadas categóricas) y `Churn`.
* **Insight:** Se creó la nueva variable **`Num_Servicios_Adicionales`**, que representa la cantidad de servicios extra contratados por el cliente. Se observó una **correlación negativa** fuerte: a **mayor cantidad de servicios adicionales**, **menor es la probabilidad de churn**. Esto sugiere que los servicios adicionales actúan como "pegamento" para la retención.
    *(Ver heatmap de correlación, boxplot y línea de tendencia de 'Num_Servicios_Adicionales' vs 'Churn' en el notebook)*

### **7. Cuentas Diarias (`Cuentas_Diarias`) vs. Churn**
Se creó una nueva característica, `Cuentas_Diarias`, para analizar el cargo mensual en una base diaria.
* **Insight:** Similar al cargo mensual, los clientes que hacen churn tienden a tener **cargos diarios promedio más altos**, lo que refuerza la hipótesis de la sensibilidad al precio o la percepción del valor.
    *(Ver histograma y boxplot de 'Cuentas_Diarias' vs 'Churn' en el notebook)*

## 🚀 Instrucciones para Ejecutar el Notebook

Para ejecutar y explorar este análisis en tu entorno local, sigue los siguientes pasos:

### **1. Prerrequisitos**
Asegúrate de tener instalado Python (versión 3.7 o superior recomendada) y las siguientes librerías:
* `pandas`
* `numpy`
* `matplotlib`
* `seaborn`
* `plotly`
* `requests`

**Descargar el Notebook**
Puedes descargar el archivo TelecomX_LATAM.ipynb directamente desde el repositorio de GitHub o clonar el repositorio completo si lo deseas.

**Abrir y Ejecutar el Notebook**
Opción A: Jupyter Notebook/JupyterLab (Local)
Abre tu terminal o símbolo del sistema.

Navega hasta el directorio donde guardaste el archivo .ipynb.

Ejecuta el comando: jupyter notebook o jupyter lab

Se abrirá una interfaz en tu navegador. Haz clic en TelecomX_LATAM.ipynb para abrir el notebook.

Una vez abierto, puedes ejecutar cada celda de código secuencialmente (clic en "Cell" -> "Run All" o Shift + Enter en cada celda).

Opción B: Google Colab (Online)
Ve a Google Colab.

Haz clic en "File" (Archivo) -> "Upload notebook" (Subir notebook).

Selecciona el archivo TelecomX_LATAM.ipynb desde tu computadora.

Una vez cargado, puedes ejecutar todas las celdas (clic en "Runtime" (Entorno de ejecución) -> "Run all" (Ejecutar todo)).

¡Disfruta explorando los datos y los insights sobre el churn en TelecomX!

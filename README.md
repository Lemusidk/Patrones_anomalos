# Detección de Anomalías: Consumo de Combustible y Emisiones (Ene 2018) 🚗💨

Este proyecto aplica técnicas de **Aprendizaje No Supervisado** para identificar vehículos con patrones de consumo y emisiones inusuales en el mercado mexicano (datos de enero 2018). Utiliza el algoritmo **Isolation Forest** para separar registros anómalos del comportamiento estándar de la industria.

## 🎯 Objetivos
* Analizar la relación entre potencia (HP), rendimiento de combustible y emisiones de CO2.
* Implementar un modelo robusto de detección de valores atípicos (outliers) multidimensionales.
* Visualizar los clústeres de anomalías para entender qué características definen a un vehículo ineficiente.

## 🛠️ Stack Tecnológico
* **Lenguaje:** Python 3.14.3
* **Librerías de Datos:** Pandas, NumPy.
* **Visualización:** Seaborn, Matplotlib (Pairplots, Heatmaps, Boxplots).
* **Machine Learning:** Scikit-Learn (`IsolationForest`, `StandardScaler`).

## 📊 Metodología Aplicada

### 1. Ingeniería y Limpieza de Datos
* Selección de variables críticas: Cilindros, Potencia, Rendimiento (Ciudad/Carretera) y CO2.
* Validación de integridad: Verificación de nulos y valores negativos.
* **Escalado Estándar:** Normalización de características para asegurar que la potencia (HP) y el rendimiento (km/l) tengan el mismo peso en el modelo.

### 2. Modelado (Isolation Forest)
Se configuró un modelo con una **tasa de contaminación del 5%**, asumiendo que una pequeña fracción de la flota presenta tecnologías obsoletas o configuraciones de alto consumo.
* **Lógica del modelo:** El algoritmo "aísla" observaciones creando particiones; las anomalías requieren menos particiones para ser aisladas.



### 3. Análisis de Resultados
* **Segmentación:** Se identificaron 229 registros anómalos (aprox. 5% del dataset).
* **Hallazgo clave:** Los vehículos etiquetados como anómalos muestran un rendimiento de combustible significativamente menor y una correlación positiva extrema con las emisiones de CO2.

## 📈 Visualizaciones Destacadas
* **Heatmap de Correlación:** Identificación de la fuerte relación inversa entre potencia y rendimiento.
* **Pairplot de Anomalías:** Visualización en múltiples dimensiones de cómo se agrupan los vehículos ineficientes.

## 📂 Estructura de Salida
Los resultados se exportan automáticamente a:
`data/model_outputs/anomalias_consumo.csv`
Incluyendo la etiqueta `Anomalia` para facilitar la toma de decisiones o auditorías energéticas.

---
*Proyecto desarrollado como parte de mi portafolio de Ciencia de Datos.*

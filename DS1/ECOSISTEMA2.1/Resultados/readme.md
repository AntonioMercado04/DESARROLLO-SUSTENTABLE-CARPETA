# Reporte de Resultados: Chatbot de Identificación de Flora y Fauna

## 1. Resumen de Desempeño
Se evaluó el modelo de clasificación y respuesta del chatbot utilizando un conjunto de prueba de 500 imágenes distribuidas uniformemente entre tres categorías: Animales, Insectos y Plantas. El sistema alcanzó una precisión general del 94.2% en la identificación a nivel de especie bajo condiciones de iluminación estándar.

---

## 2. Métricas de Rendimiento por Categoría

| Categoría | Muestras Evaluadas | Identificaciones Correctas | Precisión (%) | Tiempo Promedio de Respuesta (s) |
| :--- | :---: | :---: | :---: | :---: |
| **Plantas** | 170 | 163 | 95.8% | 1.12 s |
| **Insectos** | 165 | 151 | 91.5% | 1.35 s |
| **Animales** | 165 | 157 | 95.1% | 1.08 s |
| **TOTAL / PROMEDIO** | **500** | **471** | **94.2%** | **1.18 s** |

---

## 3. Observaciones sobre el Comportamiento del Sistema

1. **Preprocesamiento de Imagen:**
   * La calidad de la segmentación influye directamente en la tasa de acierto. Imágenes con fondos demasiado saturados o con múltiples especies en una sola toma redujeron la precisión en un 12.4%.
   
2. **Latencia y API:**
   * El tiempo promedio global de procesamiento fue de **1.18 segundos** desde la recepción del archivo hasta la generación del mensaje descriptivo.
   * La mayor latencia ocurrió en la categoría de *Insectos*, debido a la necesidad de extraer micro-características morfológicas (patrones de alas, antenas) en el análisis de visión artificial.

3. **Manejo de Excepciones:**
   * Ante imágenes borrosas, no centradas o de muy baja resolución (< 240p), el chatbot respondió correctamente solicitando una nueva toma con mejor iluminación en lugar de arrojar una predicción errónea.

---

## 4. Archivos de Respaldo

* **Reporte completo estilo IEEE:** [Resultados.pdf](Resultados/Resultados.pdf)
* **Datos raw de pruebas (CSV):** `Resultados/datos_evaluacion.csv`

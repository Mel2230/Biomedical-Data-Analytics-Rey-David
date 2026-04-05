
# 🏥 Proyecto Gestión Biomédica – Clínica Rey David

## 📊 Diagrama de Flujo del Proyecto

![Diagrama de Flujo](./diagrama_pipeline.png)

---

## 📌 Descripción del Proyecto

Este proyecto tiene como objetivo transformar un entorno de *data swamp* en una arquitectura de datos estructurada que permita la gestión eficiente de la tecnología biomédica en la Clínica Rey David.

A través de un pipeline de datos desarrollado en Python (Pandas) y un modelo analítico en Power BI, se logra integrar, limpiar y estructurar la información proveniente de múltiples fuentes, permitiendo generar indicadores clave para la toma de decisiones.

El proyecto sigue una arquitectura ETL (Extract, Transform, Load) que culmina en el desarrollo de dashboards analíticos orientados a la gestión biomédica.

---

## ⚙️ Pipeline de Datos (ETL)

### 1. 📥 Extracción (Extract)

- Archivo Excel: Inventario y Cronograma  
- Fuente financiera: DUSOFT  

Los datos son cargados en Google Colab mediante Pandas, donde se identifican estructuras y metadatos.

---

### 2. 🔄 Transformación (Transform – Python & Pandas)

- Análisis exploratorio de datos (EDA)  
- Limpieza y normalización  
- Gestión de IDs (asignación secuencial)  
- Mapeo de clasificación de riesgo (13 → 5 categorías)  
- Estandarización de texto (UPPER / Proper)  
- Tratamiento de valores nulos  
- Reestructuración del cronograma (formato ancho → largo)  

Resultado: **datos limpios y estructurados**

---

### 3. 🧩 Carga (Load – Modelo en Estrella)

#### 🔹 Dimensiones
- Dim_Equipo  
- Dim_Ubicacion  
- Dim_Clasificacion  
- Dim_Propietario  
- Dim_Tiempo  

#### 🔹 Tablas de Hechos
- Fact_Inventario  
- Fact_Cronograma  
- Fact_Costos  

---

## 📈 Transformaciones en Power BI

### 🔹 Fact_Inventario

**Fuente:** inventario_estandarizado.csv  

Transformaciones:

1. Promoción de encabezados  
2. Cambio de tipos de datos  
3. Eliminación de columnas innecesarias  
4. Formato Proper  
5. Formato Upper  
6. Upper + Proper  

---

### 🔹 Dim_Equipo

**Fuente:** dim_equipo.csv  

Transformaciones:

1. Promoción de encabezados  
2. Tipos de datos  
3. Formato Proper  
4. Formato Upper  

---

### 🔹 Tabla de Medidas (Measure)

Se crea una tabla independiente para centralizar todas las medidas DAX.

Beneficios:
- Organización del modelo  
- Mejor mantenimiento  
- Escalabilidad  

---

### 🔹 Fact_Precio_Obsolescencia

**Fuente:** Activos_Fijos_Data.csv  

Transformaciones:

1. Promoción de encabezados  
2. Tipos de datos  
3. Join con Fact_Inventario (Left Join)  
4. Expansión de columnas  
5. Renombrado de campos  

---

## 📊 Dashboards Desarrollados

### 🧾 Inventario
- Estado operativo  
- Distribución por área  
- Clasificación de riesgo  

### 💰 Costos de Equipos
- Costos de mantenimiento  
- Análisis financiero  

### ⚠️ Obsolescencia
- Vida útil  
- Índice de obsolescencia  
- Priorización de renovación  

---

## 🔗 Visualización del Dashboard

👉 https://app.powerbi.com/links/-eWl1py8rF?ctid=693cbea0-4ef9-4254-8977-76e05cb5f556&pbi_source=linkShare

---

## 🎯 Resultados

- Transformación de data swamp a datos estructurados  
- Mejora en toma de decisiones biomédicas  
- Optimización del mantenimiento  
- Identificación de riesgos y obsolescencia  
- Base para analítica predictiva  

---

## 🚀 Tecnologías Utilizadas

- Python (Pandas)  
- Google Colab  
- Power BI  
- ETL  
- Modelo de datos tipo estrella  

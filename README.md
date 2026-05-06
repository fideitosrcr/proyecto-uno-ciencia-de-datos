# Análisis de la base de datos BioTIME

![Banner de biodiversidad](https://unsplash.com/es/fotos/un-burro-con-una-silla-de-montar-KZUZ_9BmzAs)

Este proyecto implementa un **pipeline ETL (Bronce → Silver → Gold)** para procesar y analizar datos de **BioTIME**, una base de datos global de biodiversidad que contiene registros de abundancia y ocurrencia de especies a lo largo del tiempo y el espacio.

El pipeline está escrito en Python y utiliza **DuckDB** como motor de consultas, generando tablas agregadas y gráficos de tendencias de riqueza de especies, estacionalidad y acumulación de especies.

---

## 📁 Estructura del repositorio
proyecto-uno-ciencia-de-datos/

├── .gitignore

├── requirements.txt

├── README.md

├── notebooks/

│ ├── bronze.py

│ ├── silver.py

│ └── gold.py

└── datos/

│ ├── datos_crudos/ # <-- Aquí van los archivos originales de BioTIME

│ ├── biotime_v2_query_15April25.rds

│ └── biotime_v2_metadata_15April25.csv

├── bronze_output/ # Generada por bronze.py (no se sube)

├── silver_output/ # Generada por silver.py (no se sube)

├── gold_output/ # Generada por gold.py (no se sube)

└── gold_input/ # Carpeta intermedia (no se sube)



> **Nota:** Las carpetas `bronze_output`, `silver_output`, `gold_output` y `gold_input` se crean automáticamente al ejecutar los scripts. Los archivos grandes (`.duckdb`, `.parquet`) no se suben a GitHub por su tamaño (se regeneran localmente).

---

##  Descarga de los datos crudos (BioTIME)

Los datos originales **no están incluidos en el repositorio** porque su tamaño supera los límites de GitHub. Debes descargarlos manualmente desde google drive:

1. Ve a [https://drive.google.com/drive/folders/1BDi9rFRRiA_IQsG8xXXNf1E4q7Zxq5GZ?usp=sharing)
2. Coloca ambos archivos en la carpeta `datos/datos_crudos/` de este repositorio.

**Alternativa rápida (si ya tienes los archivos en otra ubicación):**  
Cópialos desde tu sistema local a `P:\proyecto_1\datos\datos_crudos\` (o la ruta donde clonaste el repositorio).

---

##  Requisitos previos

- **Python 3.8 o superior**
- **Git** (para clonar el repositorio)
- **Espacio en disco**: al menos 10 GB libres (los datos procesados generan archivos temporales grandes).

---

##  Clonar el repositorio

```bash
git clone https://github.com/fideitosrcr/proyecto-uno-ciencia-de-datos.git
cd proyecto-uno-ciencia-de-datos

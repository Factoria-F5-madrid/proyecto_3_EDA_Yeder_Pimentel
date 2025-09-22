# Video Game Sales — EDA (Kaggle: rush4ratio)

**Proyecto:** Exploratory Data Analysis (EDA) sobre ventas de videojuegos con ratings.  
**Dataset:** `Video_Games_Sales_as_at_22_Dec_2016.csv` (rush4ratio / Kaggle).  
**Notebook principal:** `video_game_sales_EDA.ipynb`

---

## 🎯 Objetivo
Preparar un dataset limpio, realizar un EDA completo y entregar un informe ejecutivo con hallazgos accionables para presentar al CEO.  

El análisis incluye:
- Limpieza y preprocesado del dataset
- Visualizaciones descriptivas
- Análisis por **plataforma**, **género**, **publisher** y **región**
- Evaluación de la relación entre **puntuaciones (críticos/usuarios)** y **ventas globales**
- Generación automática de un **informe ejecutivo** en Markdown

---

## 📂 Estructura del repositorio
<img width="773" height="252" alt="image" src="https://github.com/user-attachments/assets/6e3fb056-9d96-44e9-a9ab-1c3ce809eef6" />


---

## ⚙️ Requisitos (instalación)
Se recomienda usar un entorno virtual:

---

## ⚙️ Requisitos (instalación)

Se recomienda usar un entorno virtual:
```bash
python -m venv .venv

# macOS / Linux
source .venv/bin/activate

# Windows (PowerShell)
.\.venv\Scripts\Activate.ps1

pip install -r requirements.txt
```

## 📥 Cómo obtener y colocar el dataset

1. Descarga `Video_Games_Sales_as_at_22_Dec_2016.csv` desde Kaggle  
   (o usa `kaggle datasets download -d rush4ratio/video-game-sales-with-ratings` si tienes la API).

2. Coloca el archivo en la carpeta `data/`:
<img width="512" height="106" alt="image" src="https://github.com/user-attachments/assets/21de14d7-be8d-44f1-8e05-fa033e889839" />

⚠️ La carpeta `data/` está en `.gitignore` → el dataset no se subirá al repo de GitHub.

---

## 🚀 Uso del notebook

1. Abre `video_game_sales_EDA.ipynb` en VS Code (extensión Jupyter) o JupyterLab.

2. Ejecuta las celdas en orden:
   - Carga del dataset original
   - Exploración inicial (tipos, nulos, estadísticos)
   - Enhanced cleaning (normalización, tipos, tratamiento de tbd, duplicados)
   - Visualizaciones:
     - 📊 Ventas por plataforma
     - 🎮 Ventas por género
     - 🏢 Ventas por publisher
     - 🌍 Distribución por regiones
     - 🔗 Correlaciones (scores vs ventas)
   - Guardado de:
     - `data/video_game_sales_clean.csv` (dataset limpio)
     - `data/executive_summary.md` (informe ejecutivo)

---

## 🧹 Proceso de limpieza (resumen)

- Normalización de nombres de columnas (snake_case)
- Conversión de `year` a entero válido (eliminando años irreales)
- Normalización de `platform` (PS4, PS3, X360, NS, …)
- Conversión de `user_score` y `critic_score` a numérico ('tbd' → NaN, escala unificada)
- Conversión de columnas de ventas a numérico (y eliminación de valores negativos)
- Eliminación de filas sin `title` o `global_sales`
- Eliminación de duplicados por `(title, platform, year)` conservando la fila con mayor `global_sales`
- Creación de `avg_score` (media entre crítico y usuario)

---

## 📊 Entregables

- `video_game_sales_EDA.ipynb` — Notebook ejecutado y comentado
- `data/video_game_sales_clean.csv` — Dataset limpio (local, no en repo)
- `data/executive_summary.md` — Informe ejecutivo generado automáticamente
- Repositorio GitHub con commits claros (conventional commits)

# Tarea 3: Polars — Credit Card Fraud Detection

**LEAD University · Prof. Johansell Villalobos Cubillo · 2026**

---

## ¿Qué hace este proyecto?

Predice si una transacción con tarjeta de crédito es **fraudulenta** (`Class = 1`) o **legítima** (`Class = 0`), comparando el rendimiento de **Polars vs Pandas** en cada etapa del procesamiento.

---

## Informe final

El análisis completo (descripción del dataset, EDA, ingeniería de características, resultados de Machine Learning, benchmark Polars vs Pandas, experimentos de escalabilidad y Lazy Execution, respuestas a las preguntas de análisis y conclusiones) está documentado en:

📄 [`report/Tarea_3_Guissell_Betancur_v2.pdf`](report/Tarea_3_Guissell_Betancur_v2.pdf)

---

## Dataset

| Campo | Detalle |
|-------|---------|
| Nombre | Credit Card Fraud Detection |
| Fuente | https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud |
| Filas | 284 807 transacciones |
| Columnas | 31 (Time, V1–V28, Amount, Class) |
| Objetivo | `Class`: 0 = legítima · 1 = fraude |

### Cómo descargar

```bash
# Opción 1: Kaggle CLI
pip install kaggle
kaggle datasets download -d mlg-ulb/creditcardfraud
unzip creditcardfraud.zip -d data/raw/

# Opción 2: Descarga manual
# Ir a la URL de Kaggle → Download → guardar creditcard.csv en data/raw/
```

---

## Estructura del proyecto

```
project/
├── data/
│   ├── raw/
│   │   └── creditcard.csv       ← CSV descargado de Kaggle
│   └── processed/                ← Datos intermedios generados por el notebook
├── notebooks/
│   └── analysis.ipynb            ← Notebook principal (todo el pipeline)
├── figures/                       ← Gráficas generadas
├── results/                       ← Resultados en CSV
├── report/
│   └── Tarea_3_Guissell_Betancur_v2.pdf   ← Informe final con análisis y conclusiones
└── requirements.txt
```

---

## Instalación

```bash
# 1. Clonar el repositorio
git clone <URL_DEL_REPO>
cd project

# 2. Crear entorno virtual
python -m venv .venv
source .venv/bin/activate     # Linux / macOS
.venv\Scripts\activate        # Windows

# 3. Instalar dependencias
pip install -r requirements.txt
```

---

## Ejecución

```bash
# Abrir el proyecto en VS Code
code .
# → Abrir notebooks/analysis.ipynb (extensión Jupyter de VS Code)
# → Seleccionar el kernel del entorno virtual (.venv) y ejecutar todas las celdas
```

---

## Contenido del notebook

| Sección | Descripción |
|---------|-------------|
| 0 | Importaciones y configuración del entorno |
| 1 | Análisis Exploratorio (EDA) con Polars |
| 2 | Ingeniería de características con Polars |
| 3 | Entrenamiento de 3 modelos ML |
| 4 | Benchmark Polars vs Pandas |
| 5 | Experimento: escalabilidad (25/50/75/100%) |
| 6 | Experimento: Lazy vs Eager Execution |

---

## Modelos entrenados

| Modelo | Librería |
|--------|---------|
| Regresión Logística | Scikit-Learn |
| Random Forest | Scikit-Learn |
| XGBoost | XGBoost |

Métricas: **Accuracy, F1, AUC-ROC**, Matriz de confusión, Tiempo de entrenamiento.

---

## Resultados generados

| Archivo | Contenido |
|---------|-----------|
| `results/benchmark.csv` | Tiempos Polars vs Pandas por etapa |
| `results/escalabilidad.csv` | Speedup al 25/50/75/100% del dataset |
| `results/resultados_modelos.csv` | Métricas de los tres modelos |

---
*Tarea 3 · Ciencia de Datos · LEAD University 2026*

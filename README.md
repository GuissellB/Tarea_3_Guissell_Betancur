# Tarea 3: Polars — Credit Card Fraud Detection

**LEAD University · Prof. Johansell Villalobos Cubillo · 2026**

---

## ¿Qué hace este proyecto?

Predice si una transacción con tarjeta de crédito es **fraudulenta** (`Class = 1`) o **legítima** (`Class = 0`), comparando el rendimiento de **Polars vs Pandas** en cada etapa del procesamiento.

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
│   ├── analysis.ipynb            ← Notebook principal (todo el pipeline)
│   ├── analysis.html             ← Exportación HTML del notebook ejecutado
│   └── analysis.pdf              ← Exportación PDF del notebook ejecutado
├── figures/                       ← Gráficas generadas
├── results/                       ← Resultados en CSV
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
# Abrir JupyterLab
jupyter lab
# → Abrir notebooks/analysis.ipynb y ejecutar todas las celdas
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
| 7 | Análisis de resultados (10 preguntas) |

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

## Commits sugeridos (Git)

```bash
git commit -m "feat: estructura inicial del proyecto"
git commit -m "feat: EDA con Polars - secciones 1.1 a 1.6"
git commit -m "feat: pipeline de preprocesamiento Polars y Pandas"
git commit -m "feat: entrenamiento de modelos ML"
git commit -m "feat: benchmark y experimentos de escalabilidad"
git commit -m "feat: experimento Lazy vs Eager"
git commit -m "docs: análisis de resultados y README final"
```

---

*Tarea 3 · Ciencia de Datos · LEAD University 2026*

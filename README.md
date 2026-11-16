# 💸 ¿Influye la financiación en la supervivencia y el éxito de las startups?

Análisis exploratorio de datos (EDA) en Python sobre **66.367 startups** y **114.949 rondas de financiación** del registro público de **Crunchbase**, para responder a una pregunta que se hacen fundadores e inversores:

> ¿Recibir más dinero hace que una startup sobreviva más y tenga más probabilidades de ser adquirida o salir a bolsa?

![Tasas de éxito y cierre por tramo de financiación](src/img/06_tasas_por_tramo.png)

## 🔑 Principales hallazgos

*(Startups con al menos 5 años de recorrido, primera ronda ≤ 2010, n = 19.382)*

| | Dato |
|---|---|
| 📈 **Más dinero, más éxito** | La tasa de éxito (adquisición/IPO) pasa del **6,5 %** (< 0,5 M$) al **38,4 %** (> 50 M$) |
| 🛟 **Más dinero, menos cierres** | La tasa de cierre baja del **21,5 %** al **7,3 %** |
| 🔁 **Importa más "cuántas veces" que "cuánto"** | Con el mismo dinero total, pasar de 1 a 5+ rondas reduce el cierre del 18,6 % al 6,7 % |
| 📉 **Rendimientos decrecientes** | El éxito toca techo con 3–4 rondas (~31 %) y baja con 5+ |
| 🇺🇸 **El país importa** | EE. UU.: 27,8 % de éxito vs. 12–18 % en Europa e India |

⚠️ Correlación no implica causalidad: las buenas startups también atraen más dinero.

## 🗂️ Estructura del repositorio

```
├── README.md
├── requirements.txt
├── presentacion/
│   ├── Presentacion_Startups_Financiacion.pptx   # presentación (público no técnico)
│   └── Presentacion_Startups_Financiacion.pdf
└── src/
    ├── memoria.ipynb            # 📒 memoria completa del análisis
    ├── data/
    │   ├── raw/                 # datos originales de Crunchbase (.csv.gz)
    │   └── processed/           # dataset limpio y enriquecido
    ├── notebooks/               # notebooks de pruebas
    ├── utils/                   # módulos propios
    │   ├── data_cleaning.py     # carga y limpieza
    │   ├── features.py          # creación de variables
    │   ├── stats_tests.py       # estadísticos y tests de hipótesis
    │   └── plots.py             # gráficos con estilo común
    └── img/                     # gráficos exportados
```

## 🛠️ Tecnologías

**Python 3** · **pandas** · **NumPy** · **Matplotlib** · **Seaborn** · **SciPy** (chi-cuadrado, Mann-Whitney, Kruskal-Wallis, Spearman) · **Jupyter**

## ▶️ Cómo reproducirlo

```bash
pip install -r requirements.txt
cd src
jupyter notebook memoria.ipynb
```

## 📚 Fuente de datos

Crunchbase Open Data Export (2015) — [notpeter/crunchbase-data](https://github.com/notpeter/crunchbase-data) (mismo dataset que *"Startup Investments"* en Kaggle).

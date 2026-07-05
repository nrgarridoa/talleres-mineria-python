![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Reproducible](https://img.shields.io/badge/Seed%20Fija-2026-0068FF?style=for-the-badge&logo=octopusdeploy&logoColor=white)

#### Si te resulta util este proyecto, apoyalo con un [![Star](https://img.shields.io/github/stars/nrgarridoa/talleres-mineria-python?style=social)](https://github.com/nrgarridoa/talleres-mineria-python/stargazers) en el repositorio.

---

# Talleres · Python aplicado a Minería

> **La ley de corte y la vibración de una voladura son decisiones de todos los dias en operacion. No hace falta una caja negra para sostenerlas con evidencia: un modelo simple, bien validado y reproducible, alcanza.**

Aqui subo los notebooks y datasets reproducibles que acompañan los articulos tecnicos de mi portafolio ([nrgarridoa.github.io](https://nrgarridoa.github.io)). Cada carpeta es un taller autocontenido — el notebook con el analisis paso a paso y el dataset para replicarlo. Todos fijan una semilla (`2026`) y corren de principio a fin sin intervencion manual.

[![Ver articulos en el portafolio](https://img.shields.io/badge/Ver%20articulos-nrgarridoa.github.io-0068FF?style=for-the-badge&logo=readdotcv&logoColor=white)](https://nrgarridoa.github.io/articles/)

---

## Vista previa

| Mineral / Estéril — Frontera de decisión | Mineral / Estéril — Curva ROC |
|:---:|:---:|
| ![Frontera de decisión](screenshots/mineral-esteril-frontera.png) | ![Curva ROC](screenshots/mineral-esteril-roc.png) |

| Vibraciones — Ajuste USBM (log-log) | Vibraciones — Predicción por carga |
|:---:|:---:|
| ![Ajuste USBM](screenshots/vibraciones-ppv-ajuste.png) | ![Predicción por carga](screenshots/vibraciones-ppv-prediccion.png) |

---

## Talleres

| Taller | Tema | Técnica | Artículo |
|---|---|---|---|
| [`mineral-esteril`](mineral-esteril/) | Clasificar mineral y estéril en un pórfido Cu-Mo a partir de ley de Cu y Mo | Regresión logística + validación cruzada | [Leer](https://nrgarridoa.github.io/articles/mineral-esteril/) |
| [`vibraciones-ppv`](vibraciones-ppv/) | Predecir la vibración (PPV) de una voladura según distancia y carga | Modelo USBM (regresión log-log) | [Leer](https://nrgarridoa.github.io/articles/vibraciones/) |

---

## Hallazgos clave

**Mineral / Estéril**
- La regresión logística con dos variables geoquímicas (Cu, Mo) alcanza **AUC ≈ 0.93** y **~89 % de acierto**, validado con 5-fold CV (AUC 0.929 ± 0.043).
- El modelo recupera la dirección del *ground truth*: el **Cu domina la decisión** (~3× el peso de Mo), consistente con la geoquímica de un pórfido Cu-Mo.
- El umbral de decisión no queda fijo en 0.5: se ajusta minimizando el costo total según cuánto cuesta diluir (falso positivo) frente a perder mineral (falso negativo).

**Vibraciones (PPV / USBM)**
- Modelo ajustado: **PPV = 1065 · SD⁻¹·⁶¹⁸⁵** (R² = 0.956 en espacio log-log), muy cerca del sitio simulado (K=1000, β=1.60).
- Validación cruzada 5-fold estable: **R² = 0.952 ± 0.011**.
- Residuos normales (Shapiro-Wilk, p = 0.128) → los **intervalos de predicción al 95 %** son válidos para diseño conservador.
- Se traduce directo a reglas de campo: carga máxima por retardo y distancia mínima segura según el límite normativo (NTP, USBM).

---

## Estructura del repositorio

```
talleres-mineria-python/
|
|-- README.md
|-- LICENSE
|-- requirements.txt
|
|-- screenshots/
|   |-- mineral-esteril-frontera.png
|   |-- mineral-esteril-roc.png
|   |-- vibraciones-ppv-ajuste.png
|   |-- vibraciones-ppv-prediccion.png
|
|-- mineral-esteril/
|   |-- notebooks/
|   |   |-- mineral-esteril.ipynb
|   |-- data/raw/
|       |-- mineral_esteril.csv
|
|-- vibraciones-ppv/
    |-- notebooks/
    |   |-- vibraciones-ppv.ipynb
    |-- data/raw/
        |-- blasting_vibration_data.csv
```

---

## Cómo ejecutar

1. **Clonar el repositorio**
   ```
   git clone https://github.com/nrgarridoa/talleres-mineria-python.git
   ```

2. **Instalar dependencias**
   ```
   pip install -r requirements.txt
   ```

3. **Abrir el taller**
   ```
   jupyter lab
   ```
   Abre el notebook del taller que te interese y ejecútalo de arriba a abajo. Cada uno fija su propia semilla y regenera su dataset en `data/raw/`.

---

## Stack tecnológico

| Herramienta | Uso |
|---|---|
| **Python** | Lenguaje base de los talleres |
| **pandas / NumPy** | Manipulación y generación de datos sintéticos |
| **scikit-learn** | Regresión logística, escalado, validación cruzada |
| **SciPy** | Regresión log-log (USBM), test de Shapiro-Wilk |
| **Matplotlib** | Visualización: EDA, fronteras, curvas de ajuste, residuos |
| **Jupyter Lab** | Entorno de ejecución de los notebooks |
| **Git / GitHub** | Versionamiento y publicación |

---

## Autor

### Nilson Rolando Garrido Asenjo

**Mining Engineer | Data Analyst | Power BI Developer**

[![Portfolio](https://img.shields.io/badge/Portfolio-nrgarridoa.github.io-0068FF?style=for-the-badge&logo=github&logoColor=white)](https://nrgarridoa.github.io)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-nrgarridoa-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/nrgarridoa)
[![YouTube](https://img.shields.io/badge/YouTube-nrgarridoa-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://www.youtube.com/@nrgarridoa)
[![Gmail](https://img.shields.io/badge/Gmail-nrgarridoa@gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:nrgarridoa@gmail.com)

Ingeniero de Minas (UNC, primer puesto) y Administrador Industrial (SENATI) con trayectoria en gran mineria, industria farmaceutica y manufactura de alimentos. He liderado equipos de campo en Newmont Yanacocha, Gold Fields y Silver Mountain, dirigido proyectos tecnologicos en CODEa UNI y ejecutado consultoria de reconciliacion de mineral para Chinalco y reportabilidad operativa para Antamina.

Mi enfoque es transformar datos operativos en inteligencia para la toma de decisiones, combinando experiencia de campo con herramientas como Power BI, Python, SQL y DAX. Piloto de drones con operaciones en superficie (fotogrametria, volumetria) y en subterranea (LiDAR con Elios 3 para Flyability). Docente de Power BI y Python aplicado a mineria.

Formacion continua en Platzi, Coursera, iSE-Latam y Netzun en analitica de datos, programacion, gestion agil de proyectos y tecnologias mineras.

[![GitHub](https://img.shields.io/badge/GitHub-nrgarridoa-black?style=for-the-badge&logo=github&logoColor=white)](https://github.com/nrgarridoa)

---

[MIT License](https://github.com/nrgarridoa/talleres-mineria-python/blob/main/LICENSE)

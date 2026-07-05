# Talleres · Python aplicado a minería

Notebooks y datasets reproducibles que acompañan los artículos técnicos de
[nrgarridoa.github.io](https://nrgarridoa.github.io), de **Nilson Rolando Garrido Asenjo**
(Ingeniero de Minas · Python para Minería).

Cada carpeta es un taller autocontenido: el notebook con el análisis paso a paso y el
dataset para replicarlo. Todos fijan una semilla (`2026`) y son reproducibles de principio
a fin.

## Talleres

| Taller | Tema | Artículo |
|---|---|---|
| [`mineral-esteril`](mineral-esteril/) | Clasificar mineral y estéril con regresión logística (pórfido de Cu-Mo) | [Leer](https://nrgarridoa.github.io/articles/mineral-esteril/) |

## Estructura

```
<taller>/
├── notebooks/   # el análisis reproducible (.ipynb)
└── data/raw/    # el dataset
```

## Cómo ejecutar

```bash
pip install -r requirements.txt
jupyter lab
```

Abre el notebook del taller y ejecútalo de arriba a abajo.

## Licencia

MIT — ver [LICENSE](LICENSE).

---

Nilson Rolando Garrido Asenjo · Ingeniero de Minas · Python para Minería
· [linkedin.com/in/nrgarridoa](https://www.linkedin.com/in/nrgarridoa)
· [github.com/nrgarridoa](https://github.com/nrgarridoa)

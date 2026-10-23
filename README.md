# Curso de ancestría genética global y local

Curso teórico-práctico virtual (12 h) – Universidad del Rosario.
Dirigido a médicos y biólogos: no se necesita experiencia previa en programación.

## Cómo usar las prácticas

Haz clic en el botón **Open in Colab** de cada sesión. Solo necesitas una cuenta de Google; no hay que instalar nada.

## Sesiones sincrónicas

| # | Tema | Cuaderno |
|---|---|---|
| 1 | Formatos de datos genómicos y control de calidad | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YTZ27/curso-ancestria/blob/main/notebooks/S1_formatos_y_calidad.ipynb) |
| 2 | Ancestría global: PCA y ADMIXTURE | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YTZ27/curso-ancestria/blob/main/notebooks/S2_pca_y_admixture.ipynb) |
| 3 | Ancestría local con RFMix | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YTZ27/curso-ancestria/blob/main/notebooks/S3_ancestria_local.ipynb) |
| 4 | Interpretación y aplicaciones | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YTZ27/curso-ancestria/blob/main/notebooks/S4_aplicaciones.ipynb) |

Cada sesión es independiente: no hace falta haber guardado nada de la sesión anterior.

## Teoría asincrónica

Cuatro módulos de 1 hora, uno antes de cada sesión sincrónica (ver [teoria/](teoria/)).

| Módulo | Tema | Antes de |
|---|---|---|
| 1 | Fundamentos: variación humana, SNPs, haplotipos, LD, estructura poblacional | Sesión 1 |
| 2 | Ancestría global: PCA, clustering, ADMIXTURE | Sesión 2 |
| 3 | Ancestría local: phasing, haplotipos, métodos HMM, RFMix | Sesión 3 |
| 4 | Aplicaciones: admixture mapping, PRS y ancestría, estudios latinoamericanos | Sesión 4 |

## Estructura del repositorio

- `notebooks/`: prácticas para abrir en Colab. En [notebooks/archivos_por_paso.md](notebooks/archivos_por_paso.md) se explica qué archivos genera cada paso y cuáles se usan después.
- `notebooks/preparar_datos_ancestria_local.ipynb`: prepara los datos de la sesión 3. Lo corre la instructora una sola vez; los participantes no lo usan.
- `data/`: datos del curso (ver [data/README.md](data/README.md) y [data/ancestria_local/README.md](data/ancestria_local/README.md)).
- `teoria/`: lecturas y enlaces a los videos.

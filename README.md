# Wine Linguistic Map by Variety

## La pregunta

Como mixólogo y enófilo, durante mucho tiempo me acompañó una duda simple: cuando se dice que un Carmenère tiene ciertas notas y un Merlot otras, ¿esas asociaciones aparecen de forma consistente en el lenguaje de las catas?

Este proyecto explora esa pregunta a partir de un corpus de reseñas de vino. No intenta definir la esencia química de una cepa ni sustituir una degustación. Analiza una señal distinta: qué descriptores usan con mayor frecuencia las reseñas asociadas a cada variedad.

## Qué hace el proyecto

1. Reúne reseñas que contienen una variedad y texto de cata.
2. Normaliza el texto y extrae un vocabulario de descriptores sensoriales.
3. Calcula, para cada cepa, la proporción de reseñas que menciona cada descriptor.
4. Reduce los perfiles lingüísticos a dos dimensiones para visualizar proximidad entre cepas y palabras.
5. Ofrece un mapa interactivo para explorar relaciones y comparar hasta dos cepas.

La aplicación muestra **98 cepas**, **89 descriptores curados** y **633.687 reseñas analizadas**. Los términos del mapa superan un umbral de presencia global del 1 %.

## Cómo interpretar el mapa

En el mapa, los elementos próximos tienen perfiles de lenguaje más parecidos dentro del modelo. La posición no representa geografía, calidad, precio ni una escala de “mejor” o “peor”.

- Selecciona una cepa para compararla con el perfil global ponderado.
- Selecciona una segunda cepa para contrastarlas directamente.
- El radar muestra el porcentaje de reseñas de cada perfil que menciona los descriptores elegidos.
- Las barras y etiquetas inferiores resumen diferencias y asociaciones compartidas.
- Selecciona una palabra para consultar las cepas donde su presencia relativa es mayor.

El mapa y las comparaciones usan solamente el vocabulario sensorial curado. Esto evita que palabras genéricas del corpus aparezcan como si fueran notas de cata.

## Qué no demuestra

Una asociación alta no demuestra que una característica sea intrínseca a la variedad. Las reseñas también reflejan región, productor, añada, vinificación, crianza, estilo del crítico y sesgos de cobertura del conjunto de datos. El resultado debe leerse como evidencia exploratoria sobre lenguaje de cata, no como una receta universal para reconocer una cepa.

## Notebook reproducible

El notebook [`wine_variety_language_analysis_portfolio.ipynb`](wine_variety_language_analysis_portfolio.ipynb) es el registro metodológico del proyecto. Conserva:

- carga y auditoría de las fuentes;
- limpieza y clasificación de reseñas;
- tokenización y construcción del diccionario;
- conteos por variedad y figuras exploratorias;
- reducción TF-IDF/SVD y construcción del mapa;
- exportación de los datos derivados que utiliza la página.

Los gráficos de prueba permanecen en el notebook para que un lector pueda revisar el proceso sin convertir la web pública en una galería estática.

## Datos y ejecución local

Los CSV originales no se incluyen en el repositorio. Consulta [`DATASETS.txt`](DATASETS.txt) para conocer los archivos esperados antes de ejecutar el notebook.

La página funciona como sitio estático, pero debe servirse por HTTP porque carga los JSON y el notebook mediante `fetch`:

```bash
python -m http.server 8000
```

Después abre [http://localhost:8000](http://localhost:8000). No requiere instalación ni un proceso de build.

## Estructura

```text
index.html                                      # Mapa y comparador interactivos
wine_variety_language_analysis_portfolio.ipynb  # Análisis reproducible
app/data/interactive_local_map_payload.json     # Nodos y relaciones del mapa
app/data/wine_variety_language_profiles.json    # Perfiles derivados para comparaciones
app/figures/                                    # Figuras conservadas para el notebook
DATASETS.txt                                    # Fuentes requeridas para reproducir
```

## Dependencias del notebook

Las dependencias se encuentran en [`requirements.txt`](requirements.txt). Instálalas en un entorno aislado antes de ejecutar el análisis:

```bash
python -m pip install -r requirements.txt
```

## Autor

Creado por [KinGaetes](https://github.com/KinGaetes) como proyecto de análisis de datos y exploración del lenguaje del vino.

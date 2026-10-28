# CHANGELOG
---

## [Ejercicio 5]
- Se creo la BD


## [Ejercicio 4]
- Se mapeo el modelo logico en el ipynb


## [Ejercicio 3]
- se añadio el modelo logico


## [Ejercicio 2]
- migrado de processed/port_movements_image.csv a dvc
- migrado de interim/plots a dvc
- migrado de port_log/data/raw/imgs a dvc
- Inicialización del repositorio de dvc

## [Ejercicio 1]
* Inicio del Sprint 3.
* Aplicamos correcion al changelog.md y nuevo README

## Sprint 2

### [Ejercicio 6]
- Añadidas las conclusiones correspondientes al Sprint 2.

### [Ejercicio 5]
- Análisis de los resultados obtenidos en el Sprint 2.

### [Ejercicio 4]
- Extracción de matrículas mediante OCR.
- Mapeo y cruce (*match*) de matrículas extraídas con el dataset principal.

### [Ejercicio 3]
- Incorporación de procesamiento de imágenes: conversión a escala de grises, ecualización, suavizado y detección de bordes.

### [Ejercicio 2]
- Implementación de diccionario para la separación y categorización de imágenes.

### [Ejercicio 1]
- Inicio del Sprint 2.
- Incorporación del dataset de imágenes.
- Aplicación de correcciones según las observaciones previas de la cátedra.

## Sprint 1

### [Ejercicio 7]
- Incorporación de la conclusión final en `conclusion.md`.

### [Ejercicio 6]
- Resolución de las preguntas de análisis dentro del entorno de Colab.

### [Ejercicio 5]
- Incorporación del gráfico: Infracciones con fecha válida vs. fecha inválida.
- Incorporación del gráfico: Exceso de velocidad promedio por muelle.
- Incorporación del gráfico: Total del exceso de velocidad real.
- Incorporación del gráfico: Total de infracciones por mes.
- Incorporación del gráfico: Total de infracciones por turno del día.
- Incorporación del gráfico: Top 10 matrículas más reincidentes.

### [Ejercicio 4]
- Creación de la clase `PortAnalyzer` en el notebook de Colab.
- Generación de los dataframes resultantes derivados de `PortAnalyzer`.

### [Ejercicio 3]
- Normalización de fechas de ingreso y egreso.
- Normalización de horas.
- Incorporación de la columna calculada `duracion_horas`.
- Normalización de matrículas.
- Normalización de muelles.
- Limpieza de filas con valores nulos en columnas críticas.
- Eliminación de outliers en `tonelaje_declarado` y `velocidad_ingreso`.
- Creación de la columna `exceso_velocidad_real`.
- Creación de la columna `exceso_velocidad`.
- Eliminación de filas sin infracción registrada.
- Exportación y persistencia del dataset limpio.
- Generación y guardado del resumen estadístico.

### [Ejercicio 2]
- Incorporación de la fuente de datos para el análisis.

### [Ejercicio 1]
- Implementación de la estructura base del proyecto.

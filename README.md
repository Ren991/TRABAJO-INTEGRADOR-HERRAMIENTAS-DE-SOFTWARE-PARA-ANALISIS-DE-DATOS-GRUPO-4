# TRABAJO-INTEGRADOR-HERRAMIENTAS-DE-SOFTWARE-PARA-ANALISIS-DE-DATOS-GRUPO-4

# Port Log - Sprint 2 (actual)

## 1. Objetivo
Aplicar conocimientos de tratamiento de imágenes y programación limpia sobre el contexto del sistema portuario.

## 2. Introducción y Contexto del Problema
Sprint 2 — Desarrollar

Los radares ubicados en los accesos a los muelles capturan evidencia fotográfica de las infracciones de velocidad. Las cámaras asociadas toman fotografías de la zona de proa donde está pintada la matrícula del buque. En algunos casos el sistema recorta automáticamente la zona de matrícula (`plates`); en otros, entrega la imagen completa (`completes`).

El sistema presenta las siguientes limitaciones:
* No todas las infracciones tienen imagen asociada.
* No todas las imágenes corresponden a una infracción real (falsos positivos del radar).
* Puede haber errores de detección óptica: imágenes borrosas, nocturnas o tomadas a gran distancia.

El objetivo central es responder: **¿qué infracciones tienen evidencia visual válida?**

---

# Port Log - Sprint 1

## 1. Objetivo
Aplicar conocimientos de versionado de código, organización de proyectos y análisis exploratorio de datos (EDA) utilizando la librería Pandas sobre un conjunto de datos real de operaciones portuarias. El propósito es depurar, limpiar y estructurar la información para que pueda ser incorporada sin errores en el nuevo sistema de gestión del puerto.

## 2. Introducción y Contexto del Problema
El Puerto Fluvial de Rosario es uno de los complejos portuarios más importantes de América del Sur, constituyendo el principal punto de exportación de granos y derivados de la Argentina. Diariamente ingresan y egresan decenas de buques de distintas banderas con cargas de diverso tipo.

El sistema de registro de movimientos portuarios fue migrado recientemente desde un sistema heredado de los años '90. Durante décadas, este sistema acumuló inconsistencias de formato en fechas, matrículas de buques y valores numéricos fuera de rango, generando registros erróneos que no pueden incorporarse directamente a la nueva arquitectura.

En este primer sprint, el equipo tiene la responsabilidad de analizar, depurar y normalizar el dataset histórico `port_movements.csv`, generando resúmenes estadísticos, visualizaciones de patrones de infracción y un reporte de calidad de datos que sustente el proceso de limpieza.

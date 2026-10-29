# Ejercicio 09 - Conclusión integradora

## 1. ¿Qué problema resuelve el sistema de extremo a extremo?
Toma el registro histórico de movimientos del puerto (con errores de formato
heredados), lo limpia (Sprint 1), le asocia evidencia fotográfica mediante
OCR y matching de matrículas (Sprint 2) y lo persiste en una base relacional
consultable, versionada y con búsqueda visual (Sprint 3). Permite saber qué
infracciones tienen evidencia visual y quién reincide.

## 2. Ventaja de la base vectorial frente a solo usar OCR
El OCR depende de que la matrícula sea legible: en la base final solo
97 de 474 infracciones (20,46 %) pudieron
validarse con imagen. El embedding compara la
apariencia global del buque, por lo que sirve aunque el texto esté borroso,
tapado o mal leído (ej. 0 por O), y no requiere una coincidencia exacta de
caracteres.

## 3. Limitaciones del sistema actual
- Solo hay una imagen complete por buque en la base vectorial, y los buques
  sin imagen complete quedan fuera.
- Un recorte de matrícula (plate) no se parece a una escena completa, así que
  la búsqueda por imagen falla con ese tipo de entrada.
- El matching por posición de caracteres es frágil ante caracteres
  insertados o faltantes, y el umbral de similitud es empírico.
- Hay movimientos sin radar_id registrado (radar DESCONOCIDO), lo que limita
  el análisis por radar.
- SQLite y ChromaDB locales no soportan concurrencia ni escala.

## 4. Cambios para producción en el Puerto de Rosario
- Pasar de SQLite a PostgreSQL y de ChromaDB local a un servicio gestionado.
- Guardar varias imágenes por buque y ángulo, y calibrar el umbral de
  similitud con datos reales; sumar revisión humana de coincidencias dudosas.
- Capturar mejor en origen (cámaras con iluminación nocturna, validación
  de formato de matrícula) y orquestar el pipeline con DVC y pruebas
  automáticas, con auditoría de qué versión del dataset se usó.

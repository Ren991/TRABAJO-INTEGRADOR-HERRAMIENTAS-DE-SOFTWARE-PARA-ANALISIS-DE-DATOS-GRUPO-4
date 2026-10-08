
# Ejercicio 06 — Conclusión y Diagnóstico del Sistema

### 1. ¿Qué porcentaje de las infracciones pudo validarse visualmente?
El dataset de movimientos e infracciones final cuenta con un total de **474 registros**. 
De estos, únicamente **97 infracciones pudieron ser validadas visualmente** con una imagen coincidente en el dataset procesado, lo que representa un **20.46%** de validación sobre el total del registro tabular de movimientos.


### 2. ¿Qué grupo de imágenes (`plates` o `completes`) resultó más útil para el OCR y por qué?
El grupo **`plates`**  resultó significativamente más útil y eficiente, ya que alcanzó una tasa del **100%** (60 de 60 imágenes) frente al **92.50%** (37 de 40 imágenes) del grupo `completes`.
* **Razones Técnicas:** Las imágenes del tipo `plates` reducen  drásticamente el ruido de fondo. Al alimentar al motor de OCR con una región de interés ya delimitada y de menor resolución/área promedio (26,951 px vs 221,634 px), se reduce la carga computacional y se evitan falsos positivos.

### 3. ¿Qué condiciones de captura afectaron más al matching?
Al analizar las muestras visuales y los fallos de lectura
* **Capturas nocturnas** Generan un histograma comprimido hacia los tonos oscuros donde los caracteres se confunden con el color del casco del barco.
* **Tomas desenfocadas por movimiento (blur):** Al estar el buque en tránsito o la cámara mal enfocada, los bordes de las letras se suavizan, provocando que caracteres conflictivos disminuyan el ratio de coincidencia por debajo del límite del 75%.
* **Manualmente comprobamos presencia de numeros en las imagenes, que el proceso de normalizado no transforma a letras dejando el ratio de coincidencia bajo el umbral.


### 4. Propuestas de Mejora
Para robustecer tanto la captura física de los datos como la precisión del software de análisis, sugerimos las siguientes estrategias:

* **En el Sistema de Captura (Hardware):**
  * **Iluminación Inteligente/Infraroja:** Iluminar las matriculas antes de fotografiarlas o utilizar camaras infrarojas.
  * **Multiples disparos** Disparar multiples fotografias de cada infracción.

* **En el software del puerto:**
 * Almacenar cada imagen con su metadata, para matchear no solo por imagen si no tambien por coincidencia de fecha/hora de captura.
 * Preprocesar las multiples imagenes sugeridas en el punto anterior, y selecionar automáticamente la mejor para almacenarla definitivamente


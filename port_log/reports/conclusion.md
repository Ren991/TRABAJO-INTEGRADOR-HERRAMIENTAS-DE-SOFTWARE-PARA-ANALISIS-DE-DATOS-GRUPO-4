
# Conclusión del Análisis de Movimientos Portuarios

## Evaluación de la calidad del dataset heredado

El dataset original presentó problemas de consistencia y completitud. valores nulos en columnas críticas, falta de datos en `velocidad_ingreso`  `tonelaje_declarado`  y `matricula`, valores atípicos severos, fechas y horas inválidas etc.  Después de la limpieza de 1500 registros se redujo a 893 (un 60% de datos válidos), y a los efectos del estudio solicitado, después de eliminar las filas sin infracción se redujo a 504 es decir un 33% de datos útiles para el objetivo del proyecto.

## Patrones de infracción detectados

El análisis exploratorio revela tendencias

**Turnos:** La mayor concentración de infracciones ocurre durante el turno de la madrugada 29.2% y la menor cantidad durante la mañana 21.4%
**Muelles:** El **MUELLE D** es el más conflictivo por que lidera tanto las incidencias con 91 registros, y también el exceso de velocidad promedio más alto
**Tipo de Carga:** El transporte de **TRIGO** es el rubro con más infracciones (75 casos, representando un 14.88%), seguido de cerca por el transporte de CONTENEDORES (72 casos)

## Impacto de incorporar datos sin limpieza previa

Si hubieran intentado forzar la migración de datos al nuevo sistema la presencia de strings en campos numéricos habría provocado excepciones en el tipado y las fechas y horas inválidas probablemente habrían roto cualquier métrica temporal del nuevo sistema operativo, (como cálculos de estadía negativos o nulos que podría provocar que facturen erróneamente)

## Propuesta de mejora para la captura de datos

Recomendamos reducir las anomalías en el origen de datos implementado, (o corroborando el sistema nuevo)

1) Que sea estricto respecto al tipado.
2) reemplazar campos de entrada manuales por listas desplegables para elementos como el muelle y el tipo de carga.
3) Prohibir valores negativos en donde corresponda
4) Validar fechas y horas al momento de ingresarlas, según la regla del negocio o el flujo del proceso, puede tomarse la fecha-hora directo del sistema o permitir una ventana de tiempo que el usuario puede ajustar manualmente en el campo.
5) Proteger el sistema contra outliers en datos de velocidad y tonelaje, mediante valores mínimos y máximos que obliguen al usuario( o al sistema ) a tomar la medida nuevamente antes de guardar el registro
6) Y si está dentro de las posibilidades del negocio se recomienda utilizar sistemas de medición de velocidad automáticas para eliminar el error humano y optimizar la carga de datos (medir velocidad por radar conectado al sistema)

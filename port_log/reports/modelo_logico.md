# Modelo lógico - Port Log (Sprint 3)

- Buque(id PK, matricula UNIQUE)
- Radar(id PK, radar_id UNIQUE)
- Movimiento(id PK, movimiento_id UNIQUE, buque_id FK, radar_id FK,
  fecha_ingreso, hora_ingreso, fecha_egreso, duracion_horas,
  tonelaje_declarado, velocidad_ingreso, velocidad_maxima_muelle,
  exceso_velocidad_real, exceso_velocidad, muelle, tipo_carga, origen,
  estado_despacho)
- Evidencia(id PK, movimiento_id FK UNIQUE, archivo_imagen,
  matricula_imagen, ratio, grupo)

Cardinalidades:
- Buque 1 : N Movimiento
- Radar 1 : N Movimiento
- Movimiento 1 : 0..1 Evidencia
- Movimiento N : 1 muelle (atributo); un Radar puede operar en varios muelles

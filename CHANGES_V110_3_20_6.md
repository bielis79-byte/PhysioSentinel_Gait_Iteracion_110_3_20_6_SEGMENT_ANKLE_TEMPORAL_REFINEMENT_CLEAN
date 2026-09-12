# CHANGES V110.3.20.6

- Mantiene la arquitectura segmentaria principal de V110.3.20.4.
- Refinamiento temporal aislado de tobillos q7/q14.
- q7: FIR 7 puntos, peso 0.72, cap 4.5°/frame.
- q14: FIR 9 puntos, peso 0.84, cap 4.2°/frame.
- Preserva el refinamiento previo del brazo izquierdo.
- Añade diagnóstico de ROM retenido, máximo step y aceleración proxy antes/después.
- Corrige versión de exportación de malla para heredar la versión activa de la secuencia.
- APP_VERSION = 110.3.20.6.

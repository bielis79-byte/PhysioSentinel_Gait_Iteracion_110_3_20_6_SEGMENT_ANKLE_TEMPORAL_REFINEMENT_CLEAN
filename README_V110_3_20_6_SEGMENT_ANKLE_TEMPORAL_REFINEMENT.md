# PhysioSentinel Gait V110.3.20.6

## Segment Ankle Temporal Refinement

Base: V110.3.20.4 segmentaria validada visualmente.

Esta iteración no cambia la arquitectura de retargeting segmentario. El objetivo es exclusivamente reducir la brusquedad temporal de los tobillos ya activados, especialmente q14 izquierdo, preservando la excursión conseguida.

### Cambios
- q7 derecho: FIR simétrico de 7 puntos, peso 0.72, límite 4.5°/frame, objetivo de preservar >=94% del ROM previo al limitador.
- q14 izquierdo: FIR simétrico de 9 puntos, peso 0.84, límite 4.2°/frame, objetivo de preservar >=93% del ROM previo al limitador.
- Limitador bidireccional robusto de cuatro pasadas en q7/q14.
- Frame inicial anclado exactamente a la solución segmentaria original.
- No se crea movimiento distal nuevo ni se copia el tobillo contralateral.
- Se conserva el refinamiento del brazo izquierdo de V110.3.20.4.
- Auditoría por q ampliada con ROM retenido, máximo salto y proxy de aceleración antes/después.
- Metadatos de secuencia y malla corregidos para heredar V110.3.20.6.

### Criterio de validación
La versión se considerará favorable si reduce de forma clara el máximo salto de q14 respecto a V110.3.20.4 (10.31°/frame) sin volver a congelar el tobillo ni deteriorar cadera, rodilla, pelvis o braceo. q7 también debe quedar más estable que el valor previo (~6.99°/frame).

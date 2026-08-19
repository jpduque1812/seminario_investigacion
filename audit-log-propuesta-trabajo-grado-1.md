# Audit Log — Propuesta de Trabajo de Grado

- **entregable:** Propuesta de Trabajo de Grado — "Cuando el fraude fideliza: efecto causal de la ingeniería social y su resolución sobre la deserción bancaria en Colombia"
- **fecha:** 18 de agosto de 2026
- **asesor:** Juan Carlos Muñoz Mora (Maestría en Economía Aplicada, Universidad EAFIT)
- **modo AIAS declarado:** 3 — Collaboration
- **herramientas:** [Microsoft Copilot (Opus-Claude), ggdag (R), dagitty.net]
- **conversaciones fuente:**
  1. **"Atribución de culpa en tesis"** (conversación fundacional) — definición del alcance del fraude a incluir y reformulación conceptual del marco: de *atribución de culpa* a *modalidad* y *dictamen*.
  2. "Tamaño y comparación de grupos de control" — dimensionamiento y diseño del grupo de control.
  3. "Revisión final propuesta tesis" — revisión integral y ajuste final del documento.

## Prompts clave

### Conversación 1 — "Atribución de culpa en tesis" (fundacional)
1. "¿Debo limitar el estudio a la ingeniería social o abrir el análisis a todas las modalidades de fraude?" → decisión de estudiar el **fraude en su conjunto**, con la **modalidad** como fuente de heterogeneidad.
2. "El mecanismo de atribución de culpa de Somanchi no es directamente replicable en Colombia porque la respuesta al cliente es estandarizada" → reformulación del marco: se reemplaza *atribución de culpa* por **dictamen del caso** (favorable/desfavorable = reembolso o no) como expresión de **justicia distributiva**.
3. "¿Cómo formalizo la modalidad y el dictamen dentro del DAG sin romper la estructura causal?" → incorporación de **Modalidad** como moderador y de **Dictamen** e **Impacto psicológico** como mediadores.
4. "Ajustemos objetivos y planteamiento a estos nuevos términos" → reescritura del OG, los OE y el planteamiento del problema en función de modalidad y dictamen.

### Conversación 2 — "Tamaño y comparación de grupos de control"
5. "¿El grupo de control se ve en todos los meses de corte? ¿No estaría repitiendo los mismos clientes?" → clarificación del panel a nivel cliente y del grupo *never-treated* bajo DiD escalonado.
6. "Me aumenta complejidad el volumen: ~9 millones de registros de control mensuales contra ~40 mil reclamos/mes" → estrategia de muestreo y ratio tratado:control.
7. "Reclamantes ~29.000/mes → ~900.000 clientes únicos entre 202301 y 202512; voy con 1.500.000 de grupo de control" → dimensionamiento final del grupo de control.

### Conversación 3 — "Revisión final propuesta tesis"
8. "Revisión final: sé muy crítico y claro en los puntos a mejorar" → revisión integral de planteamiento, objetivos, DAG, marco teórico, metodología y alcances.

## Aceptado de la IA
- **Reformulación conceptual central:** sustituir el marco de *atribución de culpa* (Somanchi et al., 2025) por **modalidad del fraude** (moderador) y **dictamen del caso** (mediador), reconociendo que en Colombia la respuesta al cliente es estandarizada y el reembolso es discrecional.
- **Ampliación del objeto de estudio:** pasar de un enfoque exclusivo en ingeniería social a **fraude en su conjunto**, incorporando la modalidad como fuente de heterogeneidad del efecto.
- **Fundamentación teórica del dictamen** como expresión de **justicia distributiva** en la recuperación del servicio (Smith et al., 1999; Ali et al., 2025; Liao et al., 2022) y de la modalidad vía **teoría de la atribución** y locus de causalidad (Weiner, 2000).
- **Estructura del DAG** con Modalidad (moderador), Dictamen, Confianza e Impacto psicológico (mediadores) y conjunto mínimo de ajuste {Antigüedad, Perfil cliente, Uso digital}, con justificación por referencia en las Tablas 1 y 2.
- **Estrategia de identificación** por diferencias en diferencias con adopción escalonada (Goodman-Bacon, 2021), con supuesto de tendencias paralelas condicionales.
- **Estimador primario** de Callaway y Sant'Anna (2021) y **robustez** con de Chaisemartin y D'Haultfœuille (2020); diagnóstico de pre-tendencias con event-study.
- **OE4 de descomposición de mediación causal** con múltiples mediadores (VanderWeele y Vansteelandt, 2014) y análisis de sensibilidad de Ding y VanderWeele (2016) ante confusión no observada mediador–resultado (ignorabilidad secuencial; Imai et al., 2010).
- **Confirmación del grupo de control never-treated** como panel a nivel cliente (no repetición de clientes), siguiendo a Callaway y Sant'Anna (2021).
- **Lógica de controles buenos y malos** (Cinelli et al., 2024) para excluir mediadores y modalidad del conjunto de ajuste del efecto total.
- **Magnitud económica** reforzada con Asobancaria (2025), Gupta et al. (2004) y Reichheld y Sasser (1990).

## Rechazado de la IA
- Se rechazó **mantener el marco de "atribución de culpa"** de Somanchi et al. (2025) como eje del estudio, por no ser directamente replicable en el contexto colombiano (respuesta estandarizada, reembolso discrecional); se reemplazó por **modalidad + dictamen**.
- Se rechazó **restringir el estudio solo a fraude por ingeniería social**; se amplió a fraude en su conjunto con la modalidad como moderador.
- Se descartó fijar el grupo de control en **290.000** (ratio ~1:10) por baja variabilidad; tras evaluar 1.800.000 se consolidó en **1.500.000**.
- Se rechazó incluir a los **mediadores como controles** en la estimación del efecto total (bloquearía el camino causal de interés).
- Se descartó sustentar aristas del DAG en **reportes institucionales** (p. ej. TransUnion, 2023) en lugar de fuentes académicas indexadas; se conservaron solo como contexto de magnitud.
- Se rechazó una granularidad temporal **anual** para el panel: se fijó **mensual (o mínimo trimestral)** para diagnosticar pre-tendencias y efectos dinámicos.

## Declaración
El uso de IA se enmarca en el modo **AIAS 3 (Collaboration)**: la asistencia se empleó para clarificación conceptual, reformulación del marco (modalidad y dictamen), revisión crítica, verificación de referencias y estructuración metodológica. La definición del problema, las decisiones finales (alcance del fraude, tamaño del grupo de control, criterios de depuración) y la redacción sustantiva son de autoría propia. Todas las referencias citadas fueron verificadas por el autor.
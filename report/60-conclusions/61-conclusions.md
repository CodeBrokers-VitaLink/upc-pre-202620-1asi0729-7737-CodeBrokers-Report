# 6. Conclusiones

## 6.1. Conclusiones y recomendaciones

Las entrevistas de descubrimiento identificaron información dispersa, dificultades para entender alertas y necesidad de coordinar el seguimiento entre familias y profesionales. En AV2, tres participantes del segmento familiar y uno del profesional exploraron la propuesta. Sus comentarios dan respaldo cualitativo a la utilidad de una vista centralizada y señalan que el detalle de las alertas, la lectura de mediciones y la visibilidad de los permisos todavía requieren trabajo. La muestra profesional y los registros disponibles limitan el alcance de estas conclusiones.

La revisión técnica para TB2 confirma en código una aplicación Angular conectada a una API REST de Spring Boot, con persistencia JPA, sesiones bearer opacas y acceso a datos según el vínculo con el paciente. El panel familiar reúne estado general, mediciones y alertas. El médico puede consultar pacientes y registrar intervenciones sobre alertas. El código incorpora además observaciones médicas y notificaciones internas asociadas. Se comprobó el acceso público a la Landing Page, la entrada del frontend y el contrato OpenAPI. Quedan por verificar la ejecución autenticada de los flujos, la persistencia en el entorno publicado y los resultados con usuarios de la versión final.

### Contraste con Lean UX

| Hipótesis de 1.2.2.3 | Evidencia | Resultado |
|---|---|---|
| H1. Aumentar la retención mensual en 30 % mediante un panel familiar | AV2 registra interés en consultar información centralizada. El código muestra estado y mediciones, con datos iniciales simulados. | La utilidad percibida tiene evidencia cualitativa. La retención requiere seguimiento longitudinal. |
| H2. Reducir en 50 % el tiempo para coordinar una consulta de urgencia | El producto revisado permite seguimiento de alertas. El flujo de reserva automática sigue planteado como hipótesis. | Pendientes una línea base, pruebas de coordinación y datos sobre aceptación de citas preagendadas (meta de 70 %). |
| H3. Aumentar en 40 % los convenios con clínicas | Hay directorio y registro de médicos independientes o asociados a clínicas. | Pendientes el número base de convenios y el recuento de afiliaciones activas. La meta original de 15 instituciones y la del piloto de 5 proveedores corresponden a alcances distintos. |
| H4. Confirmar el 75 % de las alertas de emergencia en cinco minutos | El código registra el seguimiento médico y contempla notificaciones sobre observaciones. | Pendientes la confirmación familiar, los canales externos del escenario y la medición de tiempos. La meta del piloto del 70 % en dos semanas mide adopción del flujo. |
| H5. Alcanzar 35 % de adopción en hogares sin seguro privado | La Landing Page comunica planes para familias y clínicas. | Pendientes el piloto en ese segmento y la validación de los convenios a tarifa social. |

El supuesto de que ambos segmentos necesitan consultar información en un solo lugar tiene apoyo cualitativo. Los supuestos sobre disponibilidad de cupos, disposición a pagar, respuesta a avisos externos y accesibilidad para adultos mayores requieren pruebas específicas. La meta BG-02 de confianza (90 % de respuestas de 4 o 5 sobre 5) también sigue pendiente de una medición con usuarios.

### Roadmap priorizado

1. **Entender y atender una alerta.** Priorizar el hallazgo de severidad 3. Aclarar gravedad, lectura vinculada y acción disponible. Repetir las tareas de 5.3 con ambos segmentos y registrar la comprensión y los bloqueos.
2. **Confirmar acceso y trazabilidad.** En un entorno autorizado, probar lectura de pacientes por cuenta, transiciones simultáneas y persistencia del estado y la intervención. Verificar con usuarios que puedan identificar quién tiene acceso a sus datos.
3. **Medir el piloto.** Identificar la versión evaluada, medir confianza y tasa de confirmación, y registrar el intervalo entre emisión y confirmación. Confirmar el canal de afiliación y la disposición a pagar con proveedores y familias.
4. **Probar funciones que requieren integraciones.** Evaluar por separado la captura desde dispositivos, el escalamiento externo y la coordinación de citas una vez que existan datos del piloto y acuerdos con proveedores.

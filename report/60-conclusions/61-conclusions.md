# 6. Conclusiones

## 6.1 Conclusiones y recomendaciones


1. VitaLink aborda la necesidad de mejorar el monitoreo preventivo y el acompañamiento de adultos mayores, facilitando el acceso a información sobre su estado de salud y la coordinación entre familiares y profesionales de salud. El proceso de Needfinding, las entrevistas y el análisis de segmentos permitieron identificar necesidades relacionadas con la comprensión de las alertas, el seguimiento del paciente y la comunicación oportuna ante situaciones de riesgo.

2. La aplicación de Domain-Driven Design permitió organizar las responsabilidades del sistema en ámbitos relacionados con el monitoreo, la gestión de emergencias y notificaciones, y la administración de usuarios y perfiles. Asimismo, la documentación mediante el C4 Model y el diseño de datos establecieron una base para orientar la implementación posterior del backend. La consistencia de esta arquitectura deberá comprobarse conforme se integren los servicios y se validen los flujos completos del producto.

3. El proceso de diseño UX/UI, apoyado en User Personas, User Journey Maps, Empathy Maps e Impact Mapping, permitió relacionar las necesidades de los usuarios con las historias y las interfaces propuestas. La Landing Page comunica la propuesta de valor de VitaLink, mientras que la primera versión de la aplicación web presenta experiencias diferenciadas para profesionales de salud y familiares. Estas interfaces constituyen una base que todavía requiere pruebas con usuarios para evaluar su claridad, accesibilidad y facilidad de uso.

4. Durante los dos primeros sprints se desarrollaron la Landing Page y una primera versión de la aplicación web utilizando Angular, con publicaciones en GitHub Pages y Vercel, respectivamente. El frontend utiliza una API de demostración para representar pacientes, alertas, mediciones e intervenciones; por ello, el avance permite mostrar las interfaces y explorar sus flujos, pero todavía no acredita el funcionamiento integral del sistema con los servicios definitivos.

5. El uso de GitFlow, ramas de desarrollo y Pull Requests permitió organizar la integración de cambios y registrar evidencias del trabajo colaborativo. Sin embargo, el seguimiento del proyecto requiere mantener una correspondencia más precisa entre el Product Backlog, las tareas del Sprint, sus estados y las evidencias de ejecución, para distinguir el trabajo implementado de las historias completamente aceptadas.

### Recomendaciones

1. Incorporar la integración con dispositivos wearables y sensores para registrar automáticamente los signos vitales de los adultos mayores, indicando la fecha, hora y origen de cada medición. Esta funcionalidad permitiría reducir el registro manual y facilitar el seguimiento continuo.

2. Implementar notificaciones push y SMS diferenciadas para familiares y profesionales de salud. Cada aviso debería comunicar la gravedad de la alerta, la situación detectada y la acción sugerida, evitando incluir información sensible innecesaria.

3. Integrar una red de cuidado que permita asignar cuidadores principales y secundarios, confirmar quién atiende una alerta y escalarla a otro responsable cuando no exista respuesta dentro del tiempo establecido.

4. Incorporar un botón de ayuda de acceso rápido para que el adulto mayor pueda solicitar asistencia. Esta función debería comunicar la solicitud a los contactos autorizados y mostrar si alguno confirmó su recepción.

5. Integrar la programación de citas y el seguimiento posterior a una alerta, permitiendo registrar evaluaciones, recomendaciones del profesional y próximas atenciones. Así se podría dar continuidad al cuidado después de resolver una situación de riesgo.

6. Incorporar recordatorios configurables de medicamentos, controles y actividades de cuidado, con confirmación de cumplimiento y avisos a los cuidadores autorizados cuando una actividad requiera seguimiento.
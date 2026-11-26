## 2.5. Ubiquitous Language

A continuación se define el glosario de términos del dominio de salud geriátrica y teleasistencia que rigen el proyecto VitaLink. Conforme al diseño guiado por el dominio (DDD), estos conceptos establecen un vocabulario riguroso, compartido y sin ambigüedades entre el equipo de desarrollo, los cuidadores y los profesionales de salud, excluyendo terminología técnica de ingeniería de software. 

Para reflejar la realidad arquitectónica, el lenguaje ubicuo se ha dividido entre los conceptos ya modelados en la capa de dominio actual y aquellos proyectados para la evolución del sistema.

### Términos Implementados en el Modelo de Dominio Actual

Los siguientes conceptos se reflejan en el contrato de la API y en las vistas revisadas para TB2.

- **Paciente (Patient).** Persona a cuyo seguimiento se vinculan las mediciones, alertas y relaciones de cuidado.
- **Medición (Record).** Registro de un indicador de un paciente, con valor, unidad y fecha. Las mediciones iniciales del alta familiar se usan para demostrar el flujo con datos simulados.
- **Rango de medición (Measurement Range).** Referencia por tipo de medición que se usa para mostrar su nivel en la interfaz. Una línea base clínica personalizada sigue siendo una propuesta.
- **Alerta de salud (Alert).** Registro asociado a un paciente que muestra tipo, gravedad y estado de atención. Los estados documentados son pendiente, en revisión y atendida.
- **Cuidador familiar (Family Caregiver).** Persona vinculada al seguimiento del paciente mediante una relación de cuidado.
- **Profesional y clínica (Doctor y Clinic).** El profesional puede registrarse como independiente o vinculado a una clínica. El registro del médico y la afiliación comercial de una institución son procesos distintos.
- **Intervención (Intervention).** Registro del cambio de estado de una alerta que identifica al actor y puede incluir una observación.
- **Relación de cuidado (Care Relationship).** Vínculo entre médico y paciente que contempla invitación y decisión sobre la relación.

### Términos Proyectados para la Evolución del Sistema

Estos conceptos forman parte de la visión a futuro del ecosistema VitaLink. Orientarán el desarrollo de nuevos servicios de backend, la integración de hardware IoT y la interconexión con plataformas de terceros:

* **Telemetría biométrica continua:** transmisión periódica de lecturas obtenidas de dispositivos de monitoreo.
* **Physiological Anomaly (Anomalía Fisiológica):**  
  Desviación temporal o sostenida de una medición biométrica respecto a los parámetros clínicos seguros establecidos para la edad y antecedentes crónicos del adulto mayor.
* **Triage Assessment (Evaluación de Triaje):**  
  Clasificación sistemática del nivel de severidad y urgencia clínica de un paciente, calculada en función de la combinación de signos vitales anómalos y síntomas reportados.
* **Assisted Appointment Scheduling (Agendamiento Asistido de Citas):**  
  Mecanismo operativo mediante el cual la plataforma pre-selecciona y aparta de forma proactiva un cupo médico disponible en un centro de salud cercano ante una alerta de riesgo.
* **Emergency Escalation (Escalamiento de Emergencia):**  
  Protocolo de comunicación progresivo que dispara alertas multicanal a contactos secundarios y servicios de emergencia en caso de que el cuidador primario no acuse recibo de una alerta crítica.
* **Fall Incident (Incidente de Caída):**  
  Evento de pérdida brusca de sustentación corporal identificado mediante patrones de acelerometría IoT.
* **Social-Rate Care (Atención a Tarifa Social):**  
  Modalidad de consulta médica ambulatoria coordinada con organizaciones de apoyo social para garantizar atención accesible a pacientes vulnerables.

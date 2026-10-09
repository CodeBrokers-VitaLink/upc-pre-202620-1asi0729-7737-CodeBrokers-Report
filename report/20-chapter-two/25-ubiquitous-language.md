## 2.5. Ubiquitous Language

A continuación se define el glosario de términos del dominio de salud geriátrica y teleasistencia que rigen el proyecto VitaLink. Conforme al diseño guiado por el dominio (DDD), estos conceptos establecen un vocabulario riguroso, compartido y sin ambigüedades entre el equipo de desarrollo, los cuidadores y los profesionales de salud, excluyendo terminología técnica de ingeniería de software. 

Para reflejar la realidad arquitectónica, el lenguaje ubicuo se ha dividido entre los conceptos ya modelados en la capa de dominio actual y aquellos proyectados para la evolución del sistema.

### Términos Implementados en el Modelo de Dominio Actual

Estos conceptos ya cuentan con representación directa a través de entidades, objetos de valor y módulos dentro de los contextos delimitados (Bounded Contexts) de la aplicación (`care` e `iam`):

* **Biometric Record / Telemetry (Registro Biométrico / Telemetría):**  
  Conjunto de lecturas continuas y parametrizadas de signos vitales transmitidas de forma periódica para evaluar el estado fisiológico del paciente.
* **Health Alert (Alerta de Salud):**  
  Notificación generada de forma automática cuando se constata un evento o anomalía que compromete la estabilidad física del paciente.
* **Measurement Range / Vital Signs Baseline (Rango de Medición / Línea Base de Signos Vitales):**  
  Rango clínico individualizado de referencia que define los valores estables para un paciente determinado, permitiendo reducir falsos positivos en la detección de riesgos.
* **Family Caregiver (Cuidador Familiar):**  
  Persona designada responsable directa del acompañamiento, toma de decisiones y respuesta ante contingencias de salud del adulto mayor en el entorno domiciliario.
* **Healthcare Provider / Professional (Proveedor de Salud / Profesional):**  
  Institución médica o especialista colegiado afiliado a la red de atención para brindar atención preventiva o de urgencia. Gestionado a través del contexto de Identidad y Acceso mediante perfiles y roles.
* **Clinical Intervention (Intervención Clínica):**  
  Acción, decisión o nota de seguimiento registrada por un cuidador o profesional de la salud en respuesta a una alerta o al estado del paciente.
* **Patient (Paciente / Adulto Mayor):**  
  Entidad principal alrededor de la cual se agrupan las alertas, intervenciones, cuidadores y registros biométricos.

### Términos Proyectados para la Evolución del Sistema

Estos conceptos forman parte de la visión a futuro del ecosistema VitaLink. Orientarán el desarrollo de nuevos servicios de backend, la integración de hardware IoT y la interconexión con plataformas de terceros:

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
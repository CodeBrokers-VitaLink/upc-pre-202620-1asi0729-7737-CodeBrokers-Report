## 2.5. Ubiquitous Language

A continuacion se define el glosario de terminos del dominio de salud geriatrica y teleasistencia que rigen el proyecto VitaLink. Conforme al diseno guiado por el dominio (DDD), estos conceptos establecen un vocabulario riguroso, compartido y sin ambiguedades entre el equipo de desarrollo, los cuidadores y los profesionales de salud, excluyendo terminologia tecnica de ingenieria de software:

* **Biometric Telemetry (Telemetria Biometrica):**  
  Conjunto de lecturas continuas y parametrizadas de signos vitales (frecuencia cardiaca, saturacion de oxigeno SpO2 y acelerometria) transmitidas de forma periodica para evaluar el estado fisiologico del paciente.

* **Physiological Anomaly (Anomalia Fisiologica):**  
  Desviacion temporal o sostenida de una medicion biometrica respecto a los parametros clinicos seguros establecidos para la edad y antecedentes cronicos del adulto mayor.

* **Critical Alert (Alerta Critica):**  
  Notificacion prioritaria generada de forma automatica cuando se constata un evento que compromete la estabilidad fisica del paciente (caida confirmada, arritmia o hipoxia aguda), requiriendo atencion inmediata.

* **Vital Signs Baseline (Linea Base de Signos Vitales):**  
  Rango clinico individualizado de referencia que define los valores estables de reposo para un paciente determinado, permitiendo reducir falsos positivos en la deteccion de riesgos.

* **Triage Assessment (Evaluacion de Triaje):**  
  Clasificacion sistematica del nivel de severidad y urgencia clinica de un paciente, calculada en funcion de la combinacion de signos vitales anomalos y sintomas reportados.

* **Family Caregiver (Cuidador Familiar):**  
  Persona designada (hijo, conyuge o tutor legal) responsable directo del acompanamiento, toma de decisiones y respuesta ante contingencias de salud del adulto mayor en el entorno domiciliario.

* **Assisted Appointment Scheduling (Agendamiento Asistido de Citas):**  
  Mecanismo operativo mediante el cual la plataforma pre-selecciona y aparta de forma proactiva un cupo medico disponible en un centro de salud cercano ante una alerta de riesgo, pendiente de confirmacion final por el cuidador.

* **Clinical Health Record (Historial Clinico Digital):**  
  Registro cronologico y consolidado de los eventos de salud, lecturas biometricas historicas, incidentes reportados y notas de evolucion emitidas por los facultativos intervinientes.

* **Healthcare Provider (Proveedor de Salud):**  
  Institucion medica, clinica ambulatoria, policlinico o especialista colegiado afiliado a la red de atencion para recibir pacientes derivados y brindar atencion preventiva o de urgencia.

* **Emergency Escalation (Escalamiento de Emergencia):**  
  Protocolo de comunicacion progresivo que dispara alertas multicanal a contactos secundarios y servicios de emergencia en caso de que el cuidador primario no acuse recibo de una alerta critica en un plazo prefijado.

* **Fall Incident (Incidente de Caida):**  
  Evento de perdida brusca de sustentacion corporal identificado mediante patrones de acelerometria y desaceleracion brusca, asociado a un alto indice de morbimortalidad en pacientes seniles.

* **Social-Rate Care (Atencion a Tarifa Social):**  
  Modalidad de consulta medica ambulatoria coordinada con organizaciones de apoyo social y policlinicos comunales para garantizar atencion accesible a pacientes vulnerables que carecen de seguro privado.


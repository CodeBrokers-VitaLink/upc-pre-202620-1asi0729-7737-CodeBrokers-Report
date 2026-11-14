## 3.2. Impact Mapping

El Impact Map de VitaLink se elaboró en UXPressia a partir de los User Personas de cada segmento objetivo ([2.3.1. User Personas](../20-chapter-two/23-needfinding.md)). Parte de tres Business Goals (BG) del piloto, identifica qué persona contribuye a cada meta, el cambio de comportamiento esperado (Impact, IM), los Deliverables del negocio digital y las User Stories que los producen ([3.1. User Stories](31-user-stories.md)).

### 3.2.1. Business Goals e Impacts

| ID | Business Goal / Impact | Actor | Métrica |
|:------|:-----------------------------------------------------|:------------------|:-----------------------------------------|
| BG-01 | Validar el canal de afiliación de proveedores de salud | Profesionales de salud | 5 proveedores afiliados en los primeros 3 meses del piloto |
| BG-02 | Ganar la confianza en el manejo de los datos de salud | Familiares y profesionales | 90 % de los familiares encuestados califica con 4 o 5 sobre 5 su confianza en el manejo de datos durante el primer mes de uso |
| BG-03 | Reducir el tiempo de respuesta de la familia ante una situación de riesgo | Familiares y adultos mayores | 70 % de los familiares registrados confirma al menos una alerta dentro de las 2 semanas posteriores a su registro |
| IM-01 | El profesional de salud comprende la propuesta, confía en ella y decide iniciar el registro institucional | Profesionales de salud | Contribuye a BG-01 |
| IM-02 | El usuario confía en la protección de los datos de salud y acepta registrar información sensible | Familiares y profesionales | Contribuye a BG-02 |
| IM-03 | El familiar se registra, comprende las alertas y las confirma con rapidez | Familiares y adultos mayores | Contribuye a BG-03 |
| IM-04 | El médico gestiona las alertas sin duplicar esfuerzos, lo que sostiene el valor operativo para su institución afiliada | Profesionales de salud | Contribuye a BG-01 |

: Business Goals e Impacts del piloto de VitaLink

### 3.2.2. Matriz de trazabilidad estratégica

| BG | Impact | Deliverable | User Stories / Technical Stories |
|:------|:------|:-------------------------------------------------|:-----------------------------------|
| BG-01 | IM-01 | Landing Page orientada a proveedores (propuesta de valor, seguridad, solicitud de información, registro de proveedor) | US-01, US-02, US-03, US-04, US-05 |
| BG-01 | IM-04 | Panel clínico de alertas (resumen, urgencia, detalle, historial, estados y observaciones) | US-11 a US-17; TS-02, TS-03, TS-04, TS-05 |
| BG-02 | IM-02 | Sección de privacidad, control de acceso por roles y aislamiento por clínica | US-07; TS-06, TS-07, TS-08, TS-11 |
| BG-03 | IM-03 | Landing Page orientada a familiares y adultos mayores | US-06, US-08, US-09, US-10 |
| BG-03 | IM-03 | Aplicación de acompañamiento familiar (estado, alertas, confirmación, historial, red de cuidado, SOS) | US-18 a US-26; TS-01, TS-09, TS-10 |

: Trazabilidad Business Goal → Impact → Deliverable → Historias

### 3.2.3. Impact Maps por segmento

#### Segmento Profesionales de Salud --- Valeria Mendoza

**BG-01: validar el canal de afiliación de proveedores de salud.** Afiliar a 5 proveedores de salud a la red de VitaLink dentro de los primeros 3 meses del piloto.

\begin{figure}[H]
\centering
\includegraphics[width=\linewidth,height=0.8\textheight,keepaspectratio]{assets/ImpactMap-Profesionales-Afiliacion.png}
\caption{Impact Map del segmento Profesionales de Salud para BG-01 (afiliación de proveedores)}
\end{figure}

**BG-02: ganar la confianza en el manejo de los datos de salud.** Lograr que el 90 % de los familiares encuestados califique con 4 o 5 sobre 5 su confianza en el manejo de datos durante el primer mes de uso.

\begin{figure}[H]
\centering
\includegraphics[width=\linewidth,height=0.8\textheight,keepaspectratio]{assets/ImpactMap-Profesionales-Confianza.png}
\caption{Impact Map del segmento Profesionales de Salud para BG-02 (confianza en el manejo de datos)}
\end{figure}

#### Segmento Familiares y Adultos Mayores --- Elena Ramírez

**BG-03: reducir el tiempo de respuesta de la familia ante una situación de riesgo.** Lograr que el 70 % de los familiares registrados en el piloto confirme al menos una alerta dentro de las 2 semanas posteriores a su registro.

\begin{figure}[H]
\centering
\includegraphics[width=\linewidth,height=0.8\textheight,keepaspectratio]{assets/ImpactMap-Familiares-TiempoRespuesta.png}
\caption{Impact Map del segmento Familiares y Adultos Mayores para BG-03 (tiempo de respuesta)}
\end{figure}

**BG-02: ganar la confianza en el manejo de los datos de salud** (meta definida en la sección 3.2.1, vista desde el segmento familiar).

\begin{figure}[H]
\centering
\includegraphics[width=\linewidth,height=0.8\textheight,keepaspectratio]{assets/ImpactMap-Familiares-Confianza.png}
\caption{Impact Map del segmento Familiares y Adultos Mayores para BG-02 (confianza en el manejo de datos)}
\end{figure}
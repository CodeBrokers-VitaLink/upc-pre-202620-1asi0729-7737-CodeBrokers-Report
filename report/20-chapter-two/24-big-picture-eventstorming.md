## 2.4. Big Picture Event Storming

#### Introducción

En esta sección se presenta el Big Picture Event Storming de VitaLink, elaborado con el objetivo de representar de manera visual los principales eventos, acciones, actores y reglas que forman parte del dominio del producto.

El análisis se realizó tomando como referencia los procesos actualmente considerados dentro de VitaLink, principalmente el monitoreo del estado de salud del adulto mayor, la gestión de alertas y la interacción de los usuarios autorizados con la plataforma. De esta manera, el artefacto permite obtener una visión general del funcionamiento del negocio antes de profundizar posteriormente en el modelado detallado de cada Bounded Context.

#### Resumen del proceso realizado

Durante la elaboración del Big Picture Event Storming se identificaron los eventos de dominio más relevantes y las acciones que los originan. Posteriormente, los elementos relacionados fueron agrupados de manera preliminar según las responsabilidades que representan dentro del dominio.

Como resultado se identificaron tres grupos principales:

1. **Monitoring Context:** agrupa los procesos relacionados con el registro y evaluación de los signos vitales del adulto mayor. Incluye eventos como el registro de signos vitales, la evaluación de las mediciones y la detección de valores considerados peligrosos.

2. **Care & Alert Management Context:** concentra las actividades relacionadas con la generación, revisión y atención de alertas de cuidado. También contempla el registro de intervenciones realizadas por el personal encargado del seguimiento del paciente.

3. **IAM Context:** agrupa las acciones relacionadas con la autenticación y gestión de sesiones de los usuarios autorizados de la plataforma.

Además de estos grupos, se identificaron elementos transversales al dominio. Entre los principales actores se encuentran el **Adulto Mayor**, el **Familiar o Cuidador Familiar** y el **Personal Médico**.

También se identificaron políticas generales del negocio, como la generación de una alerta cuando una medición alcanza un nivel considerado peligroso y el cambio progresivo del estado de una alerta durante su proceso de atención.

Finalmente, se registraron algunos hotspots relacionados con posibles conflictos en la asociación entre alertas y mediciones, así como situaciones en las que una misma alerta podría ser modificada simultáneamente.

El resultado de este análisis proporciona una visión preliminar de las responsabilidades principales del dominio y sirve como base para el posterior desarrollo del Design-Level Event Storming.

#### Diagrama de Big Picture Event Storming

\begin{center}
    \includegraphics[width=0.7\linewidth]{assets/Big_Picture_Event_Storming.png}
\end{center}


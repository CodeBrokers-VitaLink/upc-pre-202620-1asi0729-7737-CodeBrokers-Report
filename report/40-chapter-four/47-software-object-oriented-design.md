## 4.7. Software Object-Oriented Design

### 4.7.1. Class Diagrams

Los diagramas UML (Object Management Group, 2017) presentan clases y puertos seleccionados de las revisiones del Anexo A. Los signos `+` y `-` indican miembros públicos y privados. Las líneas discontinuas representan dependencias o vínculos por identificador. Las multiplicidades describen las asociaciones de dominio que permite el código. El diseño de AV2 que precedió a estas clases se conserva en el Event Storming de 4.6.1.

#### IAM

`User` representa una cuenta con un rol. `AuthSession` tiene un identificador que contiene el hash del token y comprueba su expiración. `LoginAlias` vincula un correo alternativo a la cuenta por su identificador.

\begin{figure}[H]
\centering
\includegraphics[width=\linewidth,height=0.79\textheight,keepaspectratio]{assets/diagrams/uml-iam.png}
\caption{Modelo de clases de IAM}
\end{figure}

#### Care

`CareAlert` valida las transiciones. Una atención requiere una observación y el caso de uso registra una `Intervention`. El paciente se vincula a mediciones y alertas por identificador. `CareRelationship` controla decisiones sobre el vínculo y `DoctorObservation` representa la observación que puede originar avisos por destinatario.

\begin{figure}[H]
\centering
\includegraphics[width=\linewidth,height=0.79\textheight,keepaspectratio]{assets/diagrams/uml-care.png}
\caption{Modelo de clases de seguimiento en Care}
\end{figure}

\begin{figure}[H]
\centering
\includegraphics[width=\linewidth,height=0.79\textheight,keepaspectratio]{assets/diagrams/uml-care-notes.png}
\caption{Modelo de clases de coordinación en Care}
\end{figure}

#### Providers y Enrollment

Providers distingue a los médicos independientes y los vinculados a clínicas. Enrollment integra el alta familiar con IAM, Providers y Care. `InitialVitalSigns` valida valores para la captura simulada y combina las dos lecturas de presión como una medición.

\begin{figure}[H]
\centering
\includegraphics[width=\linewidth,height=0.79\textheight,keepaspectratio]{assets/diagrams/uml-providers-enrollment.png}
\caption{Modelo de clases de Providers y Enrollment}
\end{figure}

#### Web Application

En Angular las vistas solicitan operaciones a los stores. Éstos usan modelos propios de la interfaz, servicios HTTP y puertos de aplicación. La Landing Page organiza su interacción con HTML, CSS y funciones JavaScript.

\begin{figure}[H]
\centering
\includegraphics[width=\linewidth,height=0.79\textheight,keepaspectratio]{assets/diagrams/uml-frontend.png}
\caption{Clases de presentación y estado de la Web Application}
\end{figure}

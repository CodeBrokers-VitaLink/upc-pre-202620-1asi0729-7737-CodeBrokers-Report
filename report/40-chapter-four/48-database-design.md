## 4.8. Database Design

### 4.8.1. Database Diagrams

El modelo conceptual conecta cuentas, pacientes, relaciones de cuidado y seguimiento. El modelo de dominio de 4.7 expresa reglas y casos de uso. Los siguientes diagramas aproximan el modelo físico a partir de las 14 entidades JPA y una colección de identificadores familiares en `Patient`. La estrategia de Hibernate pluraliza nombres de tablas y aplica `snake_case` a tablas y columnas. Los tipos temporales y de enums se indican por familia, dado que su representación SQL depende del dialecto. La instancia de producción no se inspeccionó.

#### IAM y Providers

Las cuentas y colegiaturas tienen restricciones de unicidad, el hash que identifica la sesión limita su longitud a 64 caracteres, y los datos de la sesión se asocian a una cuenta por ID. El identificador de clínica en Doctor es un vínculo lógico.

\begin{figure}[H]
\centering
\includegraphics[width=\linewidth,height=0.79\textheight,keepaspectratio]{assets/diagrams/er-iam-providers.png}
\caption{Persistencia inferida de IAM y Providers}
\end{figure}

#### Care

Los objetos persistidos incluyen pacientes, mediciones, rangos, alertas, intervenciones, perfiles de cuidadores, relaciones de cuidado, observaciones y notificaciones. La colección `familyIds` genera una tabla de valores vinculada a `patients`. Los restantes vínculos entre clases inspeccionadas usan campos de texto. Las versiones de pacientes, alertas y relaciones permiten detectar cambios concurrentes.

\begin{figure}[H]
\centering
\includegraphics[width=\linewidth,height=0.79\textheight,keepaspectratio]{assets/diagrams/er-care.png}
\caption{Persistencia inferida de seguimiento en Care}
\end{figure}

\begin{figure}[H]
\centering
\includegraphics[width=\linewidth,height=0.79\textheight,keepaspectratio]{assets/diagrams/er-care-notes.png}
\caption{Persistencia inferida de coordinación en Care}
\end{figure}

#### Enrollment y Shared

Enrollment delega la escritura en las entidades de IAM y Care. Shared aporta configuración y carga de catálogos. La guía de despliegue menciona un script de creación de tablas de observaciones y notificaciones. Ese script queda fuera del repositorio revisado. La configuración de producción valida el esquema con Hibernate y no lo crea por defecto.

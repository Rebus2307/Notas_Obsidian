# 🛡️ MS-900 Introducción a Microsoft 365: Descripción de las funcionalidades de seguridad y cumplimiento

## 🔗 El Concepto XDR: Rompiendo los Silos de Seguridad

Los atacantes no se limitan a un solo vector; inician con un correo de phishing (identidad/correo), toman control de una laptop (punto de conexión) y escalan privilegios para robar datos de una base de datos en la nube (aplicaciones).

Las herramientas tradicionales fallan porque alertan de forma aislada. **Microsoft Defender XDR** unifica estas señales en un solo ecosistema coordinado previo y posterior a la vulneración.

### 🧰 El Conjunto de Soluciones (*Suite*)

* **Microsoft Defender para Punto de Conexión (*Endpoint*):** Protege y detecta amenazas en dispositivos (Windows, Linux, macOS, iOS, Android) e infraestructura de red (enrutadores, firewalls).
* **Administración de Vulnerabilidades de Microsoft Defender:** Descubre y prioriza configuraciones incorrectas y vulnerabilidades (*CVE*) basadas en el riesgo real del entorno.
* **Microsoft Defender para Office 365:** Protege el correo electrónico y herramientas de colaboración (Teams, SharePoint) contra malware y phishing avanzado.
* **Microsoft Defender for Identity:** Monitorea las señales de **Active Directory local** (Domain Controllers, AD FS, AD CS) e identidades híbridas para detectar movimientos laterales y dominación de dominio.
* **Microsoft Defender for Cloud Apps:** Actúa como un **CASB** (*Cloud Access Security Broker*) proporcionando visibilidad, control de datos (DLP) y protección en aplicaciones SaaS de terceros.
* **Microsoft Defender Threat Intelligence (Defender TI):** Enriquece los IOC (Indicadores de Compromiso) con telemetría global de Microsoft para entender el contexto del atacante.

---

## ⚙️ Funcionalidades Avanzadas de Producto Cruzado

La magia de un verdadero XDR radica en lo que hace de forma automática para quitarle carga de trabajo al analista del SOC:

* **Cola de Incidentes Combinados:** En lugar de mostrar 50 alertas desconectadas, el XDR las agrupa automáticamente en **un solo Incidente**. Muestra la historia completa del ataque en una escala de tiempo unificada.
* **Interrupción Automática de Ataques (*Automatic Attack Disruption*):** Utiliza señales de alta fidelidad para contener ataques a velocidad de máquina. Puede aislar una laptop comprometida o deshabilitar una cuenta de usuario en Active Directory en tiempo real antes de que el ransomware se propague, sin esperar la aprobación humana.
* **Auto-reparación (*Self-healing*):** Emplea guías operativas automáticas (*playbooks*) para limpiar malware, eliminar correos maliciosos de los buzones y regresar los activos a un estado seguro conocido.

---

## 🌐 Microsoft Security Exposure Management (Gestión de Exposición)

A diferencia de la administración de vulnerabilidades tradicional que solo lista parches faltantes (*CVE*), esta solución trabaja a un nivel superior cruzando datos de todo el mapa de TI a través del **Gráfico de Exposición Empresarial**.

* **Rutas de Acceso a Ataques (*Attack Paths*):** Muestra visualmente cómo un atacante podría encadenar pequeñas debilidades (una laptop sin parchear + una identidad con demasiados privilegios + una base de datos expuesta) para llegar a un activo crítico.
* **Puntos de Estrangulamiento (*Choke Points*):** Identifica los nodos donde convergen múltiples rutas de ataque. Bloquear un solo punto de estrangulamiento interrumpe docenas de caminos posibles para el atacante.
* **Administración de Recursos Críticos:** Clasifica automáticamente los activos de alto valor (como controladores de dominio o bases de datos de producción) para priorizar su defensa.

---

## 🧠 Integración de Inteligencia Artificial: Security Copilot e Incidentes

La inteligencia artificial generativa se inserta directamente en el portal de Microsoft Defender para acelerar drásticamente los tiempos de investigación mediante dos modalidades:

### 💻 Experiencia Integrada en el Portal

1. **Resumen de Incidentes:** Traduce alertas técnicas complejas a un resumen ejecutivo en lenguaje natural estructurado tan pronto abres el caso.
2. **Respuestas Guiadas:** Recomienda pasos exactos de contención, investigación y remediación contextualizados al ataque actual (ej. Ransomware o Phishing).
3. **Análisis de Scripts:** Descompone código sospechoso (como un script malicioso en PowerShell ejecutado en una terminal) y explica qué hace línea por línea en lenguaje natural.
4. **Asistente de Consultas KQL:** Convierte preguntas en lenguaje natural (ej. *"Muéstrame qué dispositivos han tenido inicios de sesión fallidos en los últimos 10 minutos"*) a código **KQL** listo para ejecutarse en la búsqueda avanzada.

---

## 🤖 Agentes de IA Autónomos en el SOC

Más allá de responder a tus preguntas, Security Copilot despliega **Agentes Autónomos** especializados que trabajan en segundo plano:

* **Agente de Evaluación de Prioridades de Phishing (*Phishing Triage Agent*):** Analiza de forma autónoma los correos sospechosos reportados por los usuarios finales. Determina si es un ataque real o un falso positivo y documenta su justificación en lenguaje natural.
* **Agente de Búsqueda de Threat Hunting:** Te guía de principio a fin en una sesión de cacería de amenazas usando lenguaje natural, manteniendo el hilo conductor de tus preguntas de seguimiento.
* **Agente de Detección Dinámica de Threats:** Un servicio *backend* siempre activo que analiza anomalías sutiles que las reglas tradicionales basadas en firmas no detectaron (evitando falsos negativos) y genera alertas personalizadas mapeadas al marco **MITRE ATT&CK**.

---

## 🏛️ El Portal de Microsoft Purview y el Compliance Manager

El portal de Purview unifica la seguridad, el riesgo y la gobernanza de datos en un solo panel multinube. Su herramienta estrella de gestión es el **Compliance Manager (Administrador de Cumplimiento)**.

* **¿Qué hace?** Evalúa automáticamente el estado de cumplimiento de tu organización frente a más de 360 regulaciones globales (incluyendo normativas emergentes de Gobernanza de Inteligencia Artificial).
* **La Puntuación de Cumplimiento (*Compliance Score*):** Una métrica numérica que mide tu progreso. Se divide en:
    * *Puntos administrados por Microsoft:* Controles que Microsoft ya cumple como proveedor de infraestructura en la nube.
    * *Tus puntos:* Controles que tu organización debe implementar físicamente (procesos, configuraciones de software).

### 🔑 Elementos Clave del Administrador:

* **Controles:** Los requisitos específicos de una ley o estándar (pueden ser del cliente, de Microsoft o compartidos).
* **Evaluaciones:** Agrupaciones de controles para certificar una norma (ej. "Evaluación para ISO 27001").
* **Acciones de Mejora:** Guías paso a paso asignables a ingenieros para mitigar riesgos y subir la puntuación.

---

## 💬 Cumplimiento de Comunicaciones (*Communication Compliance*)

Es una solución de **Riesgo Interno** (*Insider Risk*) diseñada para detectar de forma proactiva conductas inapropiadas o peligrosas en los canales de texto e imagen de la empresa (Teams, Outlook, WhatsApp, Viva Engage).

* **Flujo Operativo:** Configurar (directivas) ➡️ Investigar (alertas y contextos) ➡️ Remediar (notificar, eliminar mensajes en Teams, escalar) ➡️ Mantener (auditar).
* **Casos de Uso:** Detener el acoso laboral o lenguaje ofensivo, evitar la fuga de secretos comerciales (proyectos confidenciales) y cumplir con regulaciones financieras contra el soborno o lavado de dinero.
* **Cobertura de IA Generativa:** Analiza en tiempo real los *prompts* (preguntas) y respuestas de los usuarios en **Microsoft 365 Copilot** y agentes personalizados para detectar interacciones peligrosas.
* **Integración con Security Copilot:** Permite al analista de cumplimiento pedir un **resumen contextual** del mensaje marcado por el sistema para entender la infracción de inmediato sin leer cadenas masivas de texto.

---

## 🔎 Descubrimiento Electrónico (*eDiscovery*)

Es el proceso forense y legal de buscar, preservar y exportar Información Almacenada Electrónicamente (ESI) para que sirva como **evidencia en auditorías o juicios legales**.

### ⚖️ El Flujo de Trabajo en eDiscovery:

1. **Evento Desencadenante:** Una demanda legal o investigación interna obliga a abrir un caso.
2. **Suspensiones (*Holds*):** Bloquea ubicaciones de contenido (buzones, SharePoints). Aunque el usuario intente borrar un archivo o correo incriminatorio, el sistema guarda una copia inmutable oculta para el investigador.
3. **Conjuntos de Revisión (*Review Sets*):** Copia estática de los datos en un Azure Storage seguro de Purview donde se aplica **OCR** (extraer texto de imágenes), descifrado automático de etiquetas de sensibilidad y **subprocesamiento de conversaciones** (unir chats de Teams en su contexto original).
4. **Security Copilot en eDiscovery:** El analista puede usar lenguaje natural para buscar evidencia (generando consultas *KeyQL* de forma automática) o pedirle a la IA que resuma documentos legales extensos o transcripciones de juntas en segundos.

---

## 📝 Auditoría en Purview: Estándar vs. Premium

Purview captura absolutamente cada acción de usuarios y administradores (accesos a archivos, descargas, cambios de contraseñas, interacciones con Copilot) en el **Registro de Auditoría Unificado**.

| Característica | Auditoría (Estándar) | Auditoría (Premium) |
| :--- | :--- | :--- |
| **Configuración** | Habilitada por defecto | Requiere licenciamiento avanzado |
| **Retención de Logs** | **180 días** (6 meses) | **Desde 1 año hasta 10 años** |
| **Acceso a Datos** | Buscador del portal / PowerShell | Mayor ancho de banda para APIs (SIEM) |
| **Información Inteligente** | Registra el evento básico | Registra detalles como qué buscó exactamente el usuario o si leyó/reenvió un mail |

---

## ♻️ Administración del Ciclo de Vida de los Datos

Consiste en **conservar** lo que la ley exige y **eliminar permanentemente** lo que ya no sirve para reducir la superficie de ataque de la empresa (si los datos viejos no existen, no se pueden robar en un hackeo).

* **Directivas de Retención:** Se aplican a nivel macro (ej. "Guarda todo este sitio de SharePoint por 5 años"). El contenido hereda la regla del contenedor.
* **Etiquetas de Retención:** Se aplican a nivel micro (elemento por elemento, como un archivo específico). Viajan con el archivo si se mueve dentro del inquilino.
* **Protección Adaptable:** Se integra con *Insider Risk Management*. Si el aprendizaje automático detecta que un usuario se volvió de "alto riesgo" (ej. va a renunciar), el sistema le aplica automáticamente etiquetas de retención a sus archivos para evitar que intente borrarlos de forma maliciosa.

---

## 🗃️ Administración de Registros (*Records Management*)

Es la evolución de la administración del ciclo de vida para los documentos de **máximo valor legal o regulatorio** de la empresa (contratos, registros de empleados, fórmulas de productos).

* **Restricciones de Registro:** Al declarar un archivo como "Registro", se bloquea su edición y eliminación. Si se declara como **Registro Normativo**, la restricción es **irreversible**; ni siquiera el Administrador Global puede quitar la etiqueta o acortar el tiempo de retención.
* **Retención Basada en Eventos:** El reloj de retención no empieza cuando el archivo se crea, sino cuando ocurre un evento del mundo real (ej. *"Conserva el contrato por 7 años a partir de que el contrato expire"*, o *"Guarda el expediente por 10 años a partir de que la persona deje la institución"*).
* **Revisiones de Disposición y Plan de Archivos:** Permite que revisores humanos aprueben la destrucción del registro al final de su vida útil y genera una **Prueba de Disposición** (certificado de destrucción) para los auditores.

---

## 🤝 El Portal de Confianza de Servicios (Service Trust Portal - STP)

El **STP** es el repositorio público centralizado donde Microsoft comparte con sus clientes autenticados toda la documentación e informes de auditoría elaborados por **auditores externos independientes**.

Para un analista del SOC o un auditor de GRC, este portal es la mina de oro para descargar certificaciones y validar el cumplimiento de la infraestructura en la nube.

### 📚 Categorías Clave del Contenido:

* **Certificaciones, Reglamentos y Estándares:** Contiene las auditorías y cumplimientos de marcos globales como **ISO** (ej. ISO 27001, 27018, 22301), **SOC 1/2/3**, **FedRAMP** e **HIPAA**.
* **Informes, Notas del Producto (*Whitepapers*) y Artefactos:**
    * *BCP y Recuperación ante Desastres:* Planes de continuidad empresarial.
    * *Pruebas de Lápiz (Pen Tests) y Evaluaciones:* Atestaciones de auditorías de penetración externas.
    * *Privacidad y Preguntas Frecuentes.*
* **Recursos Regionales y Sectoriales:** Documentos específicos para industrias altamente reguladas (Servicios Financieros, Ciencias de la Salud) o gobiernos (como las nubes exclusivas del Gobierno de EE. UU. o regulaciones de Singapur y la UE).
* **Recursos de la Organización:** Documentos restringidos por tu propio *tenant* según tus suscripciones y permisos de licenciamiento.

> 💡 **Tip Operativo ("Mi Biblioteca"):** Puedes guardar los documentos críticos en tu biblioteca personalizada dentro del portal y activar las **Notificaciones de actualización**. M365 te enviará un correo automático cada vez que se actualice una certificación (por ejemplo, cuando se renueve el reporte ISO anual), manteniendo tu matriz de cumplimiento siempre al día.

---

## 🔒 Los Fundamentos del Compromiso con la Privacidad

El Centro de Confianza de Microsoft estipula formalmente bajo contrato que el software y la infraestructura se diseñan bajo una estricta mentalidad de protección al usuario. Este compromiso se divide en **cuatro pilares operativos**:

```text
                  ┌─────────────────────────────────┐
                  │    CENTRO DE CONFIANZA          │
                  │         MICROSOFT               │
                  └────────────────┬────────────────┘
                                   │
         ┌─────────────────────────┼─────────────────────────┐
         ▼                         ▼                         ▼
┌─────────────────┐       ┌─────────────────┐       ┌─────────────────┐
│ CONTROL DE DATOS│       │ UBICACIÓN/RESID │       │ DEFENSA DE DATOS│
│ Tus datos te    │       │ Elige la región │       │ Desafío legal a │
│ pertenecen; no  │       │ geográfica para │       │ peticiones de   │
│ para publicidad │       │ cumplir leyes   │       │ gobiernos       │
└─────────────────┘       └─────────────────┘       └─────────────────┘
```

### A. 🛡️ Control de los Datos (Tus Datos te Pertenecen)
* Puedes acceder, modificar o destruir tu información en cualquier momento.
* Microsoft **no utiliza** tus correos, chats o archivos para entrenar publicidad ni comerciar con ellos.
* Cumplimiento estricto de la norma **ISO/IEC 27018** (el primer código internacional para la privacidad de datos personales en la nube).
* Los subprocesadores pasan auditorías previas y están encadenados contractualmente a los mismos niveles de privacidad.

### B. 📍 Saber dónde se Encuentran los Datos (Residencia de Datos)
* A través de portales como Azure o M365, el administrador elige la **región geográfica** (Datacenters) donde se almacenarán los datos en reposo.
* Esto ayuda a las organizaciones a cumplir con las leyes de soberanía de datos locales (ej. que los datos de Europa no salgan del espacio europeo o que los datos gubernamentales se queden en territorio nacional).

### C. 🔐 Protección en Reposo y en Tránsito
* **En Reposo:** Cifrado robusto con **AES-256**, con opciones de administración híbrida de llaves a través de *Azure Key Vault*.
* **En Tránsito:** Implementación forzada de protocolos seguros estándar de la industria como **TLS** e **IPsec**.
* **Cero Puntos Únicos de Riesgo:** Uso de dos o más capas de cifrado independientes.

### D. ⚖️ Defensa de los Datos (Frente a Gobiernos)
* La postura contractual de Microsoft es que **toda solicitud gubernamental de datos debe dirigirse directamente al cliente**, no al proveedor de la nube.
* Microsoft **no proporciona** "puertas traseras" (*backdoors*) ni las llaves de cifrado de la plataforma a ninguna entidad gubernamental.
* Si la ley obliga a entregar información, Microsoft revisa la validez legal del requerimiento y, si es permitido por la ley, te notificará inmediatamente con una copia de la solicitud. Microsoft tiene un historial público de demandar a gobiernos en los tribunales si los requerimientos violan el estado de derecho.
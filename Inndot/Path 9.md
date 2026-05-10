# 🛡️ Información sobre cómo Microsoft protege los datos de los clientes

## 📜 El Marco de Directivas de Microsoft (MPF)

Microsoft opera bajo un marco jerárquico que garantiza que desde el CEO hasta el desarrollador junior sigan los mismos estándares:

* **Estándares de Conducta Empresarial (SBC):** El compromiso ético y legal básico (ej. Privacidad).
* **Directivas Corporativas:** Requisitos obligatorios.
* **Procedimientos corporativos:** Los pasos específicos que el empleado debe seguir para cumplir la directiva.

### 🔒 Programa de estándares y directivas de seguridad (MSP)
Un "sub sistema" que se enfoca exclusivamente en la seguridad. Se actualiza anualmente para adaptarse a nuevas amenazas (como ataques impulsados por IA).

* **MSP (Microsoft Security Policy):** Objetivos de seguridad no técnicos para todo el personal.
* **MSPP (Microsoft Security Program Policy):** Objetivos técnicos para Equipos de desarrollo y Operaciones.
* **Estándares (O365/ ...):** Requisitos para servicios en línea y seguridad corporativa.
* **SDL (Security Development Lifecycle):** Obligatorio para cualquier ingeniero que escriba código en Microsoft, asegurando que el software sea seguro desde su diseño.

---

## 🏢 Estructura Organizativa de Microsoft 365

Microsoft 365 no es un ente aislado, es un ecosistema que colabora entre grupos:

* **Ingeniería y Dispositivos:** Donde vive Microsoft 365 (Productividad, Teams, Windows).
* **Nube e Inteligencia Artificial:** El grupo que provee la infraestructura de Azure sobre la que corre M365.
* **Equipos Transversales:**
    * Identidad: Gestiona el acceso (Microsoft Entra ID).
    * Seguridad: Respuesta centralizada a incidentes.
    * Confianza: Asegura certificados (ISO, HIPAA, FedRAMP).

Cada grupo implementa el MSP de forma propia y detalla la Directiva de Seguridad de la Información de M365.

**Cinco áreas críticas que cubre:**
1. **Infraestructura:** Hardware y redes.
2. **Software:** Aplicaciones y utilidades.
3. **Personas:** Desarrolladores y administradores.
4. **Procedimiento:** Manuales y automatizados.
5. **Datos:** El activo más valioso.

---

## ⚖️ Control de Microsoft

El marco de Microsoft 365 es una lista de 18 objetivos mínimos de seguridad (como Control de acceso, respuesta a incidentes y protección física). Microsoft audita las evidencias que luego auditores externos revisan para generar este marco.

### 🧑‍💻 Gobernanza del Personal (El factor Humano)
La seguridad física y lógica depende de quién trabaja en el sistema. Microsoft aplica un modelo riguroso:

* **Filtrado (Background Check):** Verificación de antecedentes, identidad y educación. Se repite cada 2 años para quienes tienen acceso a servicios críticos.
* **Transferencia:** Si un empleado cambia de área, el sistema de RR.HH revoca automáticamente accesos anteriores y debe solicitar nuevos permisos para su nuevo rol.
* **Rescisión:** En cuanto termina su contrato, se revoca el acceso físico y digital de forma inmediata por integración de RRHH.

---

## ⚠️ El Marco de Trabajo ERM (Enterprise Risk Management)

Microsoft no gestiona riesgos de forma aislada. Todo se alinea con el programa de Administración de Riesgos Empresariales (ERM), el cual sigue estándares internacionales como ISO 31000.

* **Propósito:** Proporcionar una metodología común para que todas las unidades (Azure, M365, Xbox) hablen el mismo idioma al evaluar amenazas.
* **Gobernanza:** Realiza evaluaciones semestrales que llegan hasta el nivel del CEO y el comité de auditoría del grupo directivo.

### 🔄 Las 4 fases de ERM en Microsoft 365
El equipo de Microsoft 365 Trust es el encargado de ejecutar estas fases de forma continua e iterativa:

**A. Identificación de Riesgos**
Es la fase de recolección de datos.
* **Entrevistas con Expertos (SME):** Los ingenieros que crean servicios explican funciones que podrían ser vulnerables.
* **Datos Técnicos:** Resultados de escaneos de vulnerabilidades, auditorías, nuevas dependencias y simulaciones de ataques (Red Team / Blue Team).

**B. Evaluación de riesgos**
Aquí se decide qué tan grave es lo que se encontró. Se utiliza la fórmula del Riesgo Residual:

`Puntuación = Impacto x Probabilidad x Deficiencia de Control`
* **Impacto:** Daño a la confidencialidad, confianza o cumplimiento.
* **Probabilidad:** Qué tan seguido ha pasado y qué tan posible es que pase de nuevo.
* **Deficiencia de Control:** Qué tan mal funciona la "cerca" que ya pusimos.

Los riesgos se clasifican en Graves, Altos, Medios y Bajos.

**Respuesta y Estrategias**
Una vez clasificado el riesgo, no todos se tratan igual. Microsoft define cuatro caminos:

| Estrategia | Descripción | Prioridad |
| :--- | :--- | :--- |
| **Mejorar** | Riesgo alto y control bajo. Requiere acción inmediata. | Máxima |
| **Supervisar** | Riesgo alto y control adecuado. Se vigila que el control no falle. | Alta |
| **Operar** | Riesgo bajo y control adecuado. Se mantiene el estándar actual. | Normal |
| **Permitir** | Riesgo bajo y control bajo. El costo de mitigación supera el beneficio. | Baja |

**Supervisión y Reporte Continuo**
El proceso nunca termina. Se realizan reuniones periódicas con los propietarios de los riesgos para actualizar las puntuaciones:
1. Si el plan de acción no funciona, se ajusta.
2. Se generan informes para la administración de Microsoft 365.
3. Estos informes alimentan el reporte global de ERM para la Junta Directiva de Microsoft.

---

## 🏗️ Arquitectura basada en Servicios Independientes

Microsoft 365 no es un bloque monolítico; es una colección de servicios independientes hospedados en centros de datos Microsoft y potenciados por Azure.

**Componentes Clave y su Hospedaje:**
* **SharePoint Online:** Utiliza máquinas virtuales de Azure, con hardware administrado específicamente por el equipo de SharePoint.
* **Office Online y Microsoft Teams:** Se ejecutan sobre máquinas virtuales de Azure, aprovechando la escalabilidad de la nube pública.
* **Exchange Online:** Se hospeda mayoritariamente en servidores físicos dedicados para maximizar el rendimiento del correo electrónico.

**Principio de Independencia:** Cada servicio es autónomo. Si Teams experimenta un fallo, SharePoint u Office Online pueden seguir funcionando, evitando un efecto dominó que afecte toda la productividad.

### 🧩 Los 6 Principios de Seguridad Arquitectónica
El marco de diseño se basa en "Confianza Cero" aplicado a la infraestructura:
1. **Privacidad de los datos:** Microsoft es el custodio, pero tú eres el dueño.
2. **Seguridad por diseño:** Uso del SDL (Security Development Lifecycle) desde la primera línea de código.
3. **Asumir vulneración:** Se asume que cualquier componente puede ser comprometido, por lo que se limita el daño que un atacante puede hacer.
4. **Defensa en profundidad:** Capas de controles (MFA, Cifrado, Supervisión) que se refuerzan entre sí.
5. **Límites de Aislamiento:** Aislamiento total en fallas de software para que un problema en un "vecino" (inquilino) no te afecte a ti.
6. **Resistencia:** Capacidad de recuperarse automáticamente de fallas de hardware o software.

### 🚧 Estrategias de Aislamiento
El aislamiento es lo que permite que una plataforma Multinquilino (Multi-tenant) sea segura:
* **Aislamiento de Red:** Restringe la comunicación entre servicios al mínimo necesario. Utiliza ACLs (Listas de Control de Acceso) y NSGs (Grupos de Seguridad de Red) de Azure. Por defecto, todo tráfico no autorizado se deniega.
* **Aislamiento de Inquilino:** Se logra lógicamente mediante Microsoft Entra ID. Cada cliente vive en un "contenedor" definido por su Unidad Organizativa (OU), lo que impide que un usuario de la Empresa A vea datos de la Empresa B.

### 🛡️ Defensa contra ataques DDoS
Microsoft utiliza su escala global para absorber ataques de Denegación de Servicio Distribuido:
* **Absorción:** Azure tiene una capacidad masiva para recibir tráfico basura sin saturarse.
* **Detección y Mitigación:** Separa la detección del tráfico en el borde de la red. Utiliza técnicas como Cookies SYN y limitación de velocidad (throttling) para proteger L3 (Red) y L4 (Transporte).

### 📈 Resiliencia y Recuperación (El 99.9%)
La resistencia no se basa en tener hardware "indestructible", sino en software inteligente.

**Resiliencia del Servicio:**
* **Activo/Activo:** Si un clúster falla, otro idéntico ya está procesando carga y asume el control sin que el usuario note el cambio.
* **Aislamiento de errores:** Evita que el error se propague a otros nodos.

**Resiliencia de Datos:**
* **Redundancy:** Los datos se replican localmente y geográficamente (en diferentes regiones).
* **Clasificación de datos:** Se prioriza la protección del contenido de cliente sobre metadatos no críticos (como el estado de "leído" de un mensaje).

---

## 🔍 Validación Continua de la Arquitectura

Microsoft no solo "diseña" la seguridad, la valida constantemente mediante:
1. **Evaluación de Configuración:** Herramientas automáticas que revisan que ningún puerto se haya abierto por error.
2. **Validación Post-Explotación:** Simulaciones de ataques reales en producción para probar si los sistemas de alerta y respuesta realmente funcionan.

### 🤝 El enfoque de respuesta federada
Microsoft no tiene un solo equipo gigante, utiliza un Modelo de Respuesta Federada. Cada servicio (Azure, M365, etc.) tiene ingenieros especializados, pero todos comparten el mismo proceso de administración de incidentes:
* Definiciones y terminología comunes.
* Entrenamiento estandarizado.
* Se apoyan en centros de inteligencia como el MSTIC (Microsoft Threat Intelligence Center) y el MSRC (Microsoft Security Response Center) para investigar vulnerabilidades y amenazas globales.

---

## 🚨 Las 4 fases de respuesta (Basadas en NIST 800-61)

La estrategia se divide en un ciclo continuo que garantiza el aprendizaje en cada evento:

**Fase 1: Preparación**
Es el trabajo preventivo antes de que ocurra algo.
* **Formación:** Entrenamiento anual obligatorio para todos los empleados.
* **Ingenieros de Guardia (OCE):** Equipos disponibles 24/7/365 con estaciones de trabajo de administración segura (SAW).
* **Equipo Rojo vs Equipo Azul:** Simulaciones de ataques reales donde el Red Team intenta infiltrarse y el Blue Team (Respuesta a Incidentes) debe detectarlos y detenerlos.

**Fase 2: Detección y Análisis**
El objetivo es encontrar señales de ataque lo antes posible.
* **Precursores e Indicadores:** Un precursor indica que algo podría pasar, un indicador confirma que algo está pasando.
* **Análisis Centralizado:** Se recolectan billones de eventos de diferentes servicios en bases de datos masivas para correlacionar registros (logs).
* **Escalación:** Si se detecta una vulneración de datos del cliente, el equipo de respuesta activa el protocolo de notificación.

**Fase 3: Contención, Erradicación y Recuperación**
* **Contención:** Limitar el daño (aislar hosts infectados, cerrar puertos).
* **Erradicación:** Eliminar la causa raíz (borrar malware, resetear secretos de cuentas comprometidas).
* **Recuperación:** Volver al "último estado bueno conocido" mediante copias de seguridad y aumentar la vigilancia para asegurar que el atacante no regrese.

**Fase 4: Actividad Posterior al incidente**
Es la fase de Mejora Continua.
* **Post mortem:** Análisis profundo de qué falló (técnico o humano).
* **Nuevas Reglas:** Se crean alertas automáticas para que el mismo problema no vuelva a ocurrir.

---

## 📩 El Proceso de Notificación al Cliente

Microsoft tiene compromisos legales estrictos. Si ocurre una vulneración de datos (pérdida, alteración o acceso no autorizado):
1. **Plazo:** Notificación en un máximo de 72 hrs tras la declaración oficial del incidente.
2. **Canales:** Centro de mensajes de M365, correo electrónico al administrador o incluso llamadas directas.
3. **Responsabilidad compartida:** Microsoft (como procesador) avisa al cliente, el cliente (como responsable) debe avisar a sus propias autoridades y usuarios finales.

### 🙋‍♂️ Responsabilidad del Cliente
Para que este sistema funcione, tú como administrador debes:
* Mantener los contactos de seguridad y privacidad actualizados en el portal.
* Configurar correctamente el acceso al centro de mensajes.
* Notificar a Microsoft de inmediato si detectas un mal uso de tus credenciales o cuentas.

---

## 🔑 Tres Pilares del Control de Acceso Crítico

Microsoft divide sus controles en tres áreas:
* **Controles de Aislamiento:** Diseñados en la arquitectura. El contenido de un cliente (ej. Pemex) está separado lógicamente del de otro (ej. IPN).
* **Controles de Personal:** Antes de que un ingeniero toque un servidor, pasa por un filtro riguroso (background check), firma acuerdos de confidencialidad y recibe capacitación anual.
* **Controles Tecnológicos:** Implementan el acceso dinámico. El código hace el trabajo, no las personas.

### 🚫 Acceso Permanente Cero (Zero Standing Access - ZSA)
Este es el concepto más importante: Nadie tiene privilegios por defecto. No hay "súper usuarios" permanentes.

**Tipos de Cuentas:**
1. **Cuentas de Equipo de Servicio:** Usadas por ingenieros de Microsoft. Tienen acceso "cero" hasta que solicitan una elevación temporal.
2. **Cuentas de Servicio:** Cuentas automatizadas (bots/código) para que los sistemas hablen entre sí. Ningún humano conoce sus contraseñas, ni tiene control sobre estas.
3. **Cuentas de cliente:** Son las que tú administras en tu portal de M365.

### 💻 Tecnologías de Protección: SAW, MFA y JIT
Para que un ingeniero de Microsoft pueda realizar una tarea de mantenimiento, debe cumplir con:
* **Estaciones de Trabajo de Acceso Seguro (SAW):** Laptops ultra-protegidas. No pueden usar USBs, no tienen Office y solo se conectan a sitios permitidos. Si la SAW no está sana, el sistema rechaza la conexión.
* **MFA (Autenticación Multifactor):** Obligatorio. Se requieren al menos dos factores (Saber, Tener).
* **JIT (Just-In-Time) y JEA (Just-Enough-Access):**
    * **JIT:** El permiso se da solo para la tarea y expira solo.
    * **JEA:** El permiso es "justo el necesario" (ej. solo leer logs, no borrar bases de datos).

---

## 🧠 Herramienta de Administración de Identidad (IDM)

El IDM es el cerebro que automatiza el ciclo de vida de las cuentas de los recursos:
* **Aprovisionamiento:** Revisa que el ingeniero tenga todos sus permisos y antecedentes al día.
* **Inactividad:** Bloquea cuentas automáticas tras 90 días sin uso.
* **Traslados y Ceses:** Si un empleado cambia de equipo o renuncia, IDM revoca accesos inmediatamente al recibir la señal del sistema de RR.HH.

### 🔐 Caja de Seguridad del Cliente (Customer Lock Box)
Si pasa un error técnico:
1. El ingeniero de Microsoft realmente necesita entrar. Aquí entra el Customer Lockbox.
2. Un gerente de Microsoft lo aprueba.
3. A ti (el cliente) te llega una notificación a tu buzón en el Centro de Administración.
4. Si tú lo apruebas, el acceso dura un máximo de 4 horas y todo queda grabado en tu registro de auditoría.

### 🚪 Traslados y Ceses: El factor RR.HH.
La seguridad está amarrada a la nómina:
* **Traslado:** Al cambiar de puesto, se debe pedir permisos nuevos desde cero. El IDM establece una fecha de expiración para borrar los accesos viejos.
* **Cese Involuntario:** En despido, se puede ejecutar una solicitud urgente que borra el acceso lógico (cuentas) y físico (insignias) en segundos.

---

## 📡 Estrategia de Recopilación Centralizada

Microsoft 365 opera a escala de millones de dispositivos, por lo que no puede registrar "todo" sin sentido. La estrategia es capturar eventos específicos, accionables y normalizados.
* **Office Data Loader (ODL):** Es el agente personalizado instalado en cada máquina de Microsoft 365. Su función es enviar los eventos cifrados (TLS 1.2+) a repositorios centrales.
* **Limpieza de datos:** Antes de que los logs salgan del servidor, el ODL elimina automáticamente información de identificación personal (PII) del cliente y lo reemplaza por un valor hash, protegiendo la privacidad desde el origen.
* **Contenido del Evento:** Para que un log sea útil, debe responder: ¿Cuándo? (en formato UTC), ¿Dónde?, ¿Quién lo hizo?, y ¿Cuál fue el resultado?

### 🎯 Eventos Auditables Críticos
Microsoft prioriza eventos que impactan la seguridad y la salud del sistema:
* **Acceso con Privilegios (JIT/Lockbox):** Cada vez que un ingeniero pide permiso para entrar al entorno, se genera un registro indestructible.
* **Comandos Ejecutados:** Si el ingeniero obtiene el acceso temporal, cada comando que teclea queda registrado y disponible para auditoría.
* **Sistemas de Detección (IDS):** Alertas de intrusiones a nivel de host y red.

---

## 🗄️ Retención y Protección de Registros

Los registros son tan valiosos que deben protegerse contra su propia modificación.
* **Inmutabilidad:** Una vez que un registro entra al sistema central, no puede ser modificado ni borrado por ingenieros (ni siquiera por los administradores de seguridad, que no tienen acceso administrativo permanente).
* **Azure Data Lake y Cosmos:**
    * **90 días:** Retención mínima estándar para la mayoría de logs para cumplir con auditorías básicas.
    * **1 año o más:** Retención en sistemas especializados (Cosmos) para investigaciones forenses de largo plazo y normativas legales.

---

## 👁️‍🗨️ Supervisión y Respuesta a Escala

Recopilar datos no sirve de nada si nadie los mira. Microsoft usa IA y Machine Learning para analizar logs en tiempo real.

**Monitoreo de Seguridad (24/7)**
* **Alertas en tiempo real:** El sistema busca patrones de ataques conocidos y anomalías.
* **Contramedidas Automatizadas:** Si el sistema detecta un ataque de fuerza bruta o movimiento lateral, Agentes Inteligentes pueden bloquear la conexión o aislar el recurso automáticamente sin intervención humana.

**Monitoreo del Estado del Servicio (Health)**
* **Recuperación Automática:** Si los logs indican que un disco está fallando o una base de datos se corrompió, el sistema inicia una "curación automática" (ej. restaurar desde una réplica geográfica) antes de que el cliente note la caída.

---

## 📝 Responsabilidad Compartida en Auditoría

Es vital recordar que Microsoft audita la infraestructura, pero tú eres responsable de auditar tu propio espacio empresarial (tenant).
* **Microsoft:** Audita el acceso de sus ingenieros y la salud de los servidores.
* **Cliente:** Debe usar el Centro de Cumplimiento de Microsoft 365 para hacer sus propias auditorías (ej. quién cambió un archivo de SharePoint o quién creó una regla de seguridad).

---

## 🩺 El Concepto PAVC: Escaneo del Estado de la Máquina

Incluso el sistema mejor diseñado se degrada (regresiones de código, configuraciones que cambian, parches olvidados). Microsoft utiliza el acrónimo **PAVC** para definir el mantenimiento de la salud de sus máquinas:

* **P (Patching - Aplicación de parches):** Gestión proactiva de actualizaciones.
* **A (Antimalware):** Protección contra software malicioso.
* **V (Vulnerability Scanning - Análisis de vulnerabilidades):** Búsqueda de fallos conocidos.
* **C (Configuration Scanning - Análisis de configuración):** Verificación de que los ajustes sigan los estándares (como los **STIG** del Departamento de Defensa).

Para lograr esto, Microsoft integra en cada recurso un agente de seguridad personalizado en colaboración con **Qualys**, garantizando visibilidad total incluso cuando el servicio escala dinámicamente.

---

## 🦠 Gestión de Parches y Antimalware

La infraestructura de Microsoft 365 prioriza las actualizaciones basándose en el riesgo real:

* **Priorización por CVSS:** Se utiliza el *Common Vulnerability Scoring System* para decidir qué parche es urgente.
* **Implementación por Fases:** Los parches se despliegan gradualmente. Si un parche rompe algo, se puede revertir antes de que afecte a toda la red global.
* **Antimalware en Tiempo Real:** Además de un escaneo completo semanal, se analizan los archivos al abrirse o ejecutarse. No solo busca firmas conocidas, sino que usa **análisis heurístico** (reconocimiento de patrones) para detectar comportamientos extraños de virus nuevos.

---

## 🔎 Análisis de Configuración y Vulnerabilidades

El agente de seguridad realiza escaneos diarios:

1. **Detección:** Busca errores de configuración (ej. un puerto abierto que debería estar cerrado).
2. **Reporte:** Los resultados van a paneles centrales para que los equipos de servicio vean las tendencias.
3. **Corrección:** Si una máquina se desvía de la "línea base" de seguridad, se marca para su corrección inmediata.

---

## ⚔️ Simulación de Ataques: Red Team vs. Blue Team

Microsoft no espera a que los hackers ataquen; se ataca a sí misma constantemente bajo la filosofía de **"Asumir la Vulneración"**.

* **Red Team (Equipo Rojo):** Empleados de Microsoft que actúan como atacantes reales. Su objetivo es infiltrarse sin ser detectados, probando qué pasa **después** de entrar (post-explotación).
* **Blue Team (Equipo Azul):** El equipo de respuesta a incidentes que debe detectar y expulsar al Red Team.
* **Emulación Automatizada:** Microsoft ha creado herramientas que lanzan ataques predefinidos de forma constante para que el Blue Team siempre tenga señales frescas que analizar y mejorar sus algoritmos de detección.

---

## 🏆 Validación Externa y Recompensas

Para no tener "ceguera de taller", Microsoft recurre a ojos externos:

* **Pruebas de Terceros:** Evaluadores certificados por **CREST** realizan auditorías anuales usando el marco de **OWASP** (las 10 vulnerabilidades web más comunes).
* **Programa de Bug Bounty:** Microsoft paga dinero a investigadores independientes por encontrar y reportar errores. Es mucho mejor pagarle a un investigador ético que dejar que un atacante venda la vulnerabilidad en el mercado negro.

---

## 🛡️ Ingeniería para la Resistencia (Anti-Fragilidad)

Microsoft asume que **todo fallará**: el hardware se romperá cada pocos segundos (a escala masiva), los humanos cometerán errores y el software tendrá bugs.

### Estrategias de Diseño:
* **Diseño Activo/Activo:** A diferencia del modelo viejo (Activo/Pasivo), aquí ambos componentes están funcionando. Si uno cae, el otro ya tiene la carga, eliminando el tiempo de conmutación.
* **Aislamiento de Fallas:** Si un componente falla, se evita el "efecto dominó". Por ejemplo, un fallo en el chat de Teams no debería impedir que accedas a tus archivos en SharePoint.
* **Radio de Explosión (*Blast Radius*):** Es el alcance del daño. Microsoft trabaja para que cada falla afecte a la menor cantidad de usuarios posible mediante la segmentación regional y lógica.

---

## 🚨 Programa de Administración de Crisis (ERCM)

El **ERCM** (Enterprise Resilience and Crisis Management) es la estructura humana y organizativa que responde cuando la tecnología no es suficiente.

* **Business Continuity Lead (BCL):** Es el "capitán" de continuidad de cada unidad (Azure, M365).

### Ciclo de Vida de BCM:
1. **Evaluación:** Identifica procesos críticos y realiza el **Análisis de Impacto Empresarial (BIA)**. Aquí se definen el **RTO** (Tiempo objetivo de recuperación) y el **RPO** (Punto objetivo de recuperación, o cuánta pérdida de datos es aceptable).
2. **Planificación:** Se escriben los planes de recuperación y se implementan tecnologías como la redundancia geográfica.
3. **Validación:** Se prueba el plan.

---

## 📊 Niveles de Validación de Capacidad

Microsoft no solo "dice" que está preparado; lo prueba con 8 niveles de rigor (del 0 al 7):

* **Niveles 1-4:** Pruebas teóricas o en entornos de laboratorio (fuera de producción).
* **Niveles 5-7:** Pruebas en **entornos de producción reales**. El nivel 7 es el máximo, donde se recupera todo un ecosistema de aplicaciones con todas sus dependencias.

> **Ejemplo Real:** Ante el huracán Harvey, el equipo de Exchange Online activó su plan y evacuó el tráfico del centro de datos de Texas de forma proactiva, evitando caídas para los usuarios.

---

## ⏱️ Supervisión de Disponibilidad y Capacidad

Incluso un sistema perfecto falla si se queda sin "gasolina" (recursos).

### Supervisión de Disponibilidad
Utiliza telemetría y alertas automáticas. Si la CPU de un servidor sube demasiado o una página principal de SharePoint no carga, el sistema puede **auto-recuperarse** redirigiendo el tráfico o escalando recursos automáticamente.

### Planeamiento de Capacidad
* **Capacity PM:** Un administrador responsable de modelar cuánta memoria, procesador y disco se necesitarán en el futuro.
* **Escenarios de Emergencia:** Se modela qué pasaría si un centro de datos entero se apaga. ¿Tiene el centro de datos de respaldo suficiente capacidad para recibir a todos los usuarios? Si la respuesta es no, se compra más hardware antes de que ocurra la crisis.

---

## ♻️ El Ciclo de Vida de Desarrollo de Seguridad (SDL)

El **SDL** es el estándar de Microsoft para reducir vulnerabilidades. No es algo que se hace al final; es un proceso que acompaña al software desde la idea hasta que se retira del mercado.

### Las 5 Fases del SDL:
1. **Requisitos:** Se definen qué leyes de privacidad y seguridad debe cumplir el software.
2. **Diseño:** Se crean **Modelos de Amenazas** (visualizar cómo un atacante podría intentar entrar).
3. **Implementación:** Se escribe el código usando herramientas aprobadas.
4. **Verificación:** Revisión manual y automática del código.
5. **Versión:** Implementación gradual en entornos de producción.

---

## 📐 Seguridad y Privacidad desde el Diseño

Microsoft utiliza el modelado de amenazas para no dejar la seguridad al azar.

* **Diagramas de Flujo de Datos (DFD):** Sirven para ver por dónde viaja la información sensible.
* **Revisión Manual del Código:** Antes de que cualquier código llegue a la "rama principal" de versión, un **revisor independiente** debe aprobarlo. No puedes aprobar tu propio código.
* **Azure DevOps Git:** Se usa para llevar un registro auditable de quién escribió qué y quién lo autorizó (se guarda por 18 meses).

---

## 🤖 Automatización de Herramientas de Seguridad

Para escalar a millones de líneas de código, Microsoft usa herramientas que analizan el software automáticamente:

| Herramienta | Función |
| :--- | :--- |
| **Análisis Estático** | Revisa el código fuente (sin ejecutarlo) buscando *passwords* olvidados o funciones inseguras. |
| **Análisis Binario** | Examina el software ya compilado para verificar la configuración del instalador. |
| **Análisis de Cifrado** | Valida que se usen algoritmos modernos y no versiones antiguas fáciles de romper. |
| **Validación de Configuración** | Revisa que el servidor de producción esté configurado según las mejores prácticas. |

---

## 🚀 El Proceso de Implementación Segura (SDP)

Una vez que el código es perfecto, no se lanza a todo el mundo al mismo tiempo. Se usa un sistema de **Anillos de Implementación**:

* **Anillo 0:** Solo el equipo que creó el servicio (pruebas internas).
* **Anillo 1:** Todos los empleados de Microsoft (uso real pero interno).
* **Anillo 2:** Primeros clientes externos (usuarios pioneros).
* **Anillo 3-N:** Despliegue global gradual hasta cubrir el 100% de la infraestructura.

---

## 🌐 Gobernanza de Código Abierto (OSS)

Microsoft usa mucho código de código abierto, pero lo hace con responsabilidad.

* **Gobernanza de Componentes (CG):** Es una herramienta automática que detecta si alguna librería externa que estás usando (como una de JavaScript o Python) tiene una vulnerabilidad conocida o problemas legales de licencia.
* **Responsabilidad:** Los ingenieros de Microsoft son responsables del código abierto que incluyen; si la librería externa falla, ellos deben arreglarla o reemplazarla.

---

## 🔐 Conceptos Fundamentales de Cifrado

El cifrado en la nube de Microsoft no es una única capa, sino un enfoque de **Defensa en Profundidad** que protege los datos en dos estados críticos:

* **Datos en Reposo:** Información almacenada en discos (SharePoint, OneDrive, buzones de Exchange).
* **Datos en Tránsito:** Información moviéndose entre el usuario y el servidor, o entre servidores de Microsoft (correos enviándose, chats de Teams en tiempo real).

Todos los métodos utilizan algoritmos conformes al estándar **FIPS 140-2** (un estándar de seguridad del gobierno de EE. UU.).

---

## 💽 Cifrado de Datos en Reposo

Microsoft aplica dos niveles de protección simultáneos:

### A. Cifrado de Nivel de Volumen (BitLocker)
Se aplica a nivel de hardware/disco duro.
* Utiliza **AES de 256 bits**.
* **Jerarquía de claves:** El sector del disco se cifra con una clave **FVEK**, esta se protege con una **VMK**, y esta última se vincula al chip **TPM** (*Trusted Platform Module*) del servidor físico.
* **Seguridad Física:** Si alguien robara físicamente un disco duro del centro de datos, no podría leer nada sin el chip TPM del servidor original y las claves de recuperación protegidas en el "almacén de secretos" de Microsoft.

### B. Cifrado de Nivel de Servicio (Aplicación)
Es una capa adicional sobre BitLocker.
* **SharePoint y OneDrive:** Cada archivo se divide en **fragmentos**. Cada fragmento se cifra con su propia clave única (AES-256). Los fragmentos cifrados se distribuyen en diferentes contenedores de Azure Storage, y las claves se guardan en un lugar separado.
* **Exchange:** Cifra los datos a nivel de buzón individual.

---

## 🔑 Administración de Claves: ¿Quién tiene la "llave"?

Existen dos modelos para gestionar las claves maestras o "raíz":

1. **Claves administradas por Microsoft:** Es la opción por defecto. Microsoft se encarga de la rotación, protección y almacenamiento de las claves en almacenes privados. Ningún empleado tiene acceso directo a ellas.
2. **Clave de Cliente (Customer Key):** El cliente (la organización) proporciona sus propias claves raíz generadas en **Azure Key Vault**.
    * **Ventaja:** Si el cliente decide dejar el servicio, puede revocar sus claves, haciendo que sus datos en la nube sean instantáneamente ilegibles (fragmentación criptográfica).
    * **Clave de Disponibilidad:** Es una "llave de repuesto" que Microsoft guarda para que, si el cliente pierde sus claves por accidente, Soporte técnico pueda ayudar a recuperar los datos y evitar su pérdida permanente.

---

## 🛤️ Cifrado de Datos en Tránsito

Protege la información mientras viaja por la red.

* **Protocolos:** Se utiliza principalmente **TLS** (*Transport Layer Security*) e **IPSec**.
* **Estándares de Certificados:** Microsoft emite certificados firmados con **SHA-2** y algoritmos **RSA** de al menos **2048 bits**.
* **Escenarios:**
    * Usuario $\leftrightarrow$ Servidor (ej. abres tu correo en el navegador).
    * Servidor de Microsoft $\leftrightarrow$ Servidor de Microsoft (ej. sincronización entre centros de datos).
    * Servidor de Microsoft $\leftrightarrow$ Servidor Externo (ej. mandas un mail a Gmail).

---

## 📝 Resumen Técnico para el Examen 🛠️

| Tecnología | Tipo de Protección | Algoritmo Típico |
| :--- | :--- | :--- |
| **BitLocker** | Nivel de Volumen (Disco) | AES-256 |
| **Cifrado de Servicio** | Nivel de Aplicación (Archivo/Buzón) | AES-256 |
| **TLS / SSL** | Datos en Tránsito | RSA (2048 bits+) |
| **FIPS 140-2** | Estándar de cumplimiento | N/A |

---

## 📜 Los 6 Principios de Privacidad de Microsoft

Microsoft opera bajo una filosofía donde la privacidad es un derecho fundamental:

1. **Control:** El cliente decide sobre sus datos.
2. **Transparencia:** Saber qué se recopila y para qué.
3. **Seguridad:** Protección mediante cifrado robusto.
4. **Protecciones legales:** Defensa de la privacidad ante gobiernos.
5. **Sin segmentación publicitaria:** Microsoft **no lee** tus correos o archivos para venderte publicidad.
6. **Beneficio para el cliente:** Los datos solo se usan para mejorar el servicio.

---

## 👥 Roles Clave y Categorías de Datos

Es vital distinguir quién es quién para entender la responsabilidad legal:

### Roles:
* **Controlador (El Cliente/Tú):** Determina por qué y cómo se procesan los datos. Eres el dueño de la información.
* **Procesador (Microsoft):** Actúa bajo tus instrucciones para prestar el servicio. No es dueño de los datos.
* **Sujeto de Datos:** La persona física identificable (ej. un alumno de la ESCOM).

### Categorías de Datos:
* **Datos del Cliente:** El contenido real (tu código, tus archivos de Excel, tus chats).
* **Datos Generados por el Servicio:** Logs de rendimiento para asegurar que Teams o Azure funcionen bien.
* **Datos de Diagnóstico:** Telemetría del software instalado (ej. si Word se crashea).
* **Datos de Servicios Profesionales:** Información compartida durante un ticket de soporte técnico.

> **Operaciones Comerciales Legítimas (LBO):** Microsoft puede usar datos seudonimizados (sin nombres) para facturación, combatir fraudes o reportes financieros, actuando aquí como controlador independiente.

---

## 🔄 El Ciclo de Vida de los Datos

Microsoft protege el dato desde que nace hasta que se destruye:

1. **Recopilación:** Regida por los **Términos de Online Services (OST)** y el **Anexo de Protección de Datos (DPA)**.
2. **Tratamiento:** Los datos se usan para la funcionalidad del servicio, solucionar problemas y mejoras continuas.
3. **Uso compartido de terceros:** Solo ocurre con **Subprocesadores** que cumplen con el estándar **SSPA** de Microsoft. Ante solicitudes de gobiernos, Microsoft exige procesos legales válidos y notifica al cliente.
4. **Retención:** Los datos se guardan cerca del cliente (residencia de datos). Características como **Retención por Litigio** permiten que los datos sean inmutables si hay un proceso legal.
5. **Destrucción:**
    * **Eliminación Activa:** Datos borrados por el usuario.
    * **Elimación Pasiva:** Al terminar la suscripción, tienes **90 días** para sacar tus datos. A los **180 días**, se borran definitivamente y son irrecuperables.

---

## 🇪🇺 El RGPD y las Solicitudes de los Interesados (DSR)

El Reglamento General de Protección de Datos de la UE es el estándar de oro. Como procesador, Microsoft te da herramientas para cumplir con los derechos de tus usuarios:

* **Derecho de Acceso/Exportación:** Obtener una copia legible por máquina de los datos.
* **Derecho de Rectificación:** Corregir datos erróneos.
* **Derecho de Eliminación (Olvido):** Borrar permanentemente los datos personales.

---

## 🤝 Responsabilidad Compartida: El ejemplo de HIPAA

Como ingeniero, este es el punto más crítico: **Microsoft garantiza que la "tubería" sea segura, pero tú eres responsable de qué echas por ella.**

* **Ejemplo:** Si un médico usa Microsoft 365 (que cumple con HIPAA), pero envía datos de un paciente a alguien que no debería por error humano, **la infracción es del médico, no de Microsoft**. Microsoft sigue las instrucciones del usuario, no analiza el contenido para decirte si estás violando una ley.

---

## 🏭 ¿Qué es un Subprocesador?

Siguiendo la terminología del **RGPD**, un subprocesador es una empresa externa que Microsoft contrata para realizar tareas que implican el procesamiento de **Datos Personales** o **Datos del Cliente**.

### Categorías de Datos involucrados:
Para que un proveedor sea considerado subprocesador, debe tocar alguna de estas categorías:
* **Datos del Cliente:** Contenido directo (archivos, emails).
* **Datos Generados por el Servicio:** Logs y métricas de rendimiento.
* **Datos de Diagnóstico:** Telemetría del software.
* **Datos de Servicios Profesionales/Soporte:** Información compartida durante una reparación.
* **Datos Confidenciales de Microsoft:** Secretos comerciales, diseños o claves de licencia.

---

## 📑 El Programa SSPA y el DPR

El **SSPA** (*Supplier Security and Privacy Assurance*) es el "pasaporte" que todo proveedor necesita para trabajar con Microsoft.

* **DPR (Data Protection Requirements):** Es el manual de instrucciones técnicas. Son controles de seguridad y privacidad que el proveedor **debe** implementar.
* **Certificación Anual:** No basta con cumplir una vez; los proveedores deben realizar una autodeclaración anual y, dependiendo del riesgo, someterse a auditorías independientes.
* **Integración con Compras:** Si un proveedor no está aprobado en el SSPA, las herramientas de compra de Microsoft bloquean automáticamente cualquier contrato o pago.

---

## 🗂️ Tipos de Subprocesadores y sus Controles

No todos los proveedores acceden a lo mismo. Microsoft los clasifica así:

1. **Tecnología:** Empresas que proporcionan software que se integra en la nube (ej. servicios de red). Pueden procesar o almacenar datos mientras el servicio corre.
2. **Auxiliares:** Empresas que dan soporte técnico o mantenimiento. Tienen acceso limitado y puntual.
3. **Personal de Contrato:** Personas externas que trabajan codo a codo con empleados de Microsoft. Se les trata como empleados: usan **SAW** (estaciones seguras), **MFA** y acceso **JIT/JEA**.

> **Dato Clave:** El personal físico de los centros de datos (seguridad, limpieza) **no puede acceder a los datos** porque estos están cifrados y ellos no tienen acceso lógico a las redes.

---

## 📢 Compromisos de Aviso al Cliente

Microsoft es transparente sobre quién toca tus datos. Según el **DPA**, existen plazos de aviso antes de agregar un nuevo subprocesador:

* **6 meses de aviso:** Para subprocesadores que tocarán **Datos del Cliente**.
* **30 días de aviso:** Para subprocesadores que tocarán otros **Datos Personales**.

---

## 🚪 El Ciclo de Vida: Incorporación y Retirada

Microsoft aplica un control estricto desde que entra un proveedor hasta que se va:

### Incorporación (Onboarding):
Antes de empezar, el proveedor pasa por:
* **Verificación Empresarial:** ¿Realmente necesitamos a este proveedor o uno existente puede hacerlo?
* **Chequeo Anticorrupción:** Revisión de antecedentes legales y reputación.
* **Sanciones Comerciales:** Verificación de que no haya prohibiciones gubernamentales para trabajar con ellos.

### Retirada (Offboarding) y Destrucción:
Cuando el contrato termina, el proveedor debe devolver o destruir los datos en un plazo de **7 días**.
* **Medios Digitales:** Deben destruirse físicamente (fragmentación/trituración) bajo estándares como **NIST** o **DoD**, de modo que los datos sean irrecuperables.
* **Material Impreso:** Almacenamiento en depósitos seguros y trituración documentada por personal de seguridad in situ.

---

## 🏰 Defensa en Profundidad: Capas del Centro de Datos

Microsoft protege sus instalaciones como fortalezas de alta seguridad. El acceso a los datos no es solo digital, sino que requiere superar múltiples barreras físicas:

* **Seguridad Perimetral:** Edificios anónimos (sin logotipos), cercas de alta seguridad, iluminación 24/7, patrullas y bolardos para evitar ataques con vehículos.
* **Control de Acceso:** Basado en el principio de **Privilegio Mínimo**. Los visitantes requieren aprobación previa, firma de acuerdos de confidencialidad y escolta permanente por personal de Microsoft.
* **Vigilancia:** Uso masivo de videovigilancia y sensores de intrusión que alertan a los Centros de Operaciones de Seguridad en tiempo real.
* **Autenticación Biométrica:** Para las áreas más críticas (como las jaulas de servidores), se requiere autenticación de dos factores, incluyendo biometría.

---

## 🌱 Gestión de Riesgos Ambientales y Sostenibilidad

Un centro de datos debe ser resistente a la naturaleza. Microsoft utiliza el proceso **TVRA (Threat, Vulnerability, and Risk Assessment)** para analizar anualmente amenazas como:

* **Riesgos Naturales:** Terremotos, huracanes e inundaciones (sensores de agua en áreas críticas).
* **Climatización:** Sistemas de HVAC de última generación para controlar el calor generado por los servidores.
* **Incendios:** Sistemas de detección y supresión de incendios con energía independiente.

### Sostenibilidad y Energía
* **Energía 24/7:** Sistemas de **UPS** (Baterías) y generadores in situ con contratos de combustible de emergencia.
* **Compromiso Verde:** Para 2025, los centros de datos funcionarán con **100% energía renovable**. Para 2030, Microsoft será **carbono negativo**.

---

## 📦 Administración y Seguridad de Activos

Cada componente físico (servidor, disco, cable) es un activo rastreado.

* **Integridad de la Cadena de Suministro:** Se vigila el hardware desde la fábrica para evitar que se instalen "puertas traseras" (firmware malicioso) durante el transporte.
* **Inventario y Clasificación:** Todo activo tiene un propietario y una etiqueta única. Los datos del cliente se clasifican con la prioridad más alta de protección.

---

## 🗄️ Seguridad de los Dispositivos de Carga de Datos (Medios Físicos)

Este es un punto crítico en auditorías de seguridad: **¿Qué pasa con los discos duros viejos?**

* **Control de Salida:** Ningún disco duro sale del área de producción. Se utilizan **arcos detectores de metales** (como en los aeropuertos) en las salidas para evitar que alguien se lleve un disco en el bolsillo.
* **Destrucción Segura:** Los discos que fallan o se retiran se someten a la normativa **NIST SP 800-88**. Se trituran o desintegran físicamente in situ para que los datos sean irrecuperables.

---

## 🏢 Resiliencia y Continuidad del Negocio

Microsoft planea para lo peor mediante el programa **ERCM** (Enterprise Resilience and Crisis Management).

* **Planes de Continuidad (BCP):** Cada centro de datos tiene su propio plan específico para su ubicación geográfica.
* **Redundancia Geográfica:** Los centros de datos están conectados por una de las redes de fibra óptica más grandes del mundo, permitiendo que si un centro de datos en Texas falla, uno en Virginia tome el control casi instantáneamente (replicación a más de 500 millas).
* **Respuesta a Pandemias:** Planes específicos para mantener la operatividad incluso con reducción de personal físico.
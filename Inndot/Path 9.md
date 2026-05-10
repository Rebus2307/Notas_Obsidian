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
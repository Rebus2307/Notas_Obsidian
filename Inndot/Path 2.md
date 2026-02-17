# ☁️ Microsoft Azure: Resumen de Estudio

> **¿Qué es Azure?** Es un conjunto de servicios en la nube que ofrece libertad para crear, administrar e implementar aplicaciones en una red global. Funciona bajo un modelo de gastos operativos (**OpEx**), pagando solo por lo que consumes.

---

## 🏗️ 1. Conceptos Básicos e Infraestructura

### Modelos de Nube
* **Nube Pública:** Servicios a través de internet público, compartidos entre varias organizaciones.
* **Nube Privada:** Uso exclusivo de recursos por parte de una sola empresa.
* **Nube Híbrida:** Combina infraestructura local (on-premises) con la nube pública.

### Jerarquía de Organización
* **Grupo de Administración:** El nivel más alto para gestionar políticas y accesos de forma masiva.
* **Suscripciones:** Proporcionan acceso autenticado. Definen el **Límite de facturación** (cómo se cobra) y el **Límite de control de acceso** (quién administra qué).
* **Grupos de Recursos:** Agrupaciones lógicas (un recurso solo puede estar en un grupo a la vez).
* **Recursos:** El bloque de creación básico (VMs, bases de datos, redes).

### Resiliencia Física
* **Regiones:** Áreas geográficas que contienen al menos tres zonas de disponibilidad.
* **Pares de Regiones:** Cada región se empareja con otra a unos 500 km para recuperación ante desastres.
* **Zonas de Disponibilidad:** Centros de datos físicamente separados dentro de una misma región.
* **Conectividad:** Unidas por redes de fibra óptica de alta velocidad propias de Microsoft.

---

## 💻 2. Servicios de Cómputo (Compute)

### Máquinas Virtuales (IaaS)
* **Uso Principal:** Control total sobre el Sistema Operativo y software personalizado.
* **Lift-and-Shift:** Ideal para mover servidores locales a la nube directamente sin rediseñar.
* **Azure Virtual Desktop (AVD):** Ejecución de escritorios y aplicaciones Windows en la nube.
* **Dominio de Actualización (Alta Disponibilidad):** Agrupa máquinas que pueden reiniciarse al mismo tiempo (evita que todas se apaguen a la vez en mantenimientos).
* **Dominio de Error (Alta Disponibilidad):** Agrupa VMs que comparten fuente de alimentación y switch de red (protege contra fallos de hardware).

### Contenedores y Serverless (PaaS)
* **Azure App Service:** Hospedaje de aplicaciones web y APIs sin gestionar infraestructura.
* **Azure Container Instances (ACI):** La forma más rápida de ejecutar un contenedor sin configurar servidores.
* **Azure Kubernetes Service (AKS):** Orquestación que administra el ciclo de vida y escalabilidad de contenedores.
* **Azure Functions (Sin estado):** Código basado en eventos que escala según demanda y se reinicia en cada respuesta.
* **Durable Functions (Con estado):** Permiten mantener el contexto y seguimiento a lo largo de varios pasos.

---

## 🌐 3. Redes y Conectividad

### Conceptos Clave
* **Virtual Networks (VNet):** Permiten la comunicación entre recursos de Azure, internet y redes locales.
* **Azure Load Balancer:** Distribuye tráfico entrante entre varias VMs (Capa 4 - TCP/UDP).
* **Azure Application Gateway:** Equilibrador de tráfico web que incluye un Firewall (WAF) (Capa 7 - HTTP/HTTPS).

### Comparativa de Conexión Híbrida
| Característica | 🔒 VPN Gateway | 🚀 ExpressRoute |
| :--- | :--- | :--- |
| **Medio** | Túnel cifrado a través de internet público. | Conexión privada dedicada de extremo a extremo. |
| **Seguridad** | Protege información evitando intercepciones. | Máxima seguridad al evitar la red pública de internet. |
| **Velocidad** | Depende del tráfico de internet. | Hasta 100 Gbps con latencias constantes. |

---

## 💾 4. Almacenamiento (Azure Storage)

### Servicios Principales
1. **Blobs:** Almacenamiento de objetos masivos no estructurados (imágenes, backups).
2. **Files:** Recursos compartidos de archivos administrados (protocolo SMB).
3. **Queues:** Mensajería para comunicación asíncrona entre aplicaciones.
4. **Disks:** Volúmenes a nivel de bloque para máquinas virtuales.

### Niveles de Acceso (Tiers) y Redundancia
* **Frecuente (Hot) vs Esporádico (Cool):** Uso diario constante vs. almacenamiento de al menos 30 días con poco acceso.
* **Archivo (Archive):** Para datos de más de 180 días. Almacenaje muy barato, pero recuperación lenta y costosa.
* **LRS (Local):** 3 copias en un solo centro de datos (la opción más barata).
* **ZRS (Zonal):** 3 copias en edificios diferentes de la misma región.
* **GRS (Geográfica):** Réplica asincrónica a una región secundaria distante (6 copias en total).
* **GZRS (Zonal-Geo):** ZRS en la primaria y LRS en la secundaria (máxima resistencia).

---

## 🛡️ 5. Identidad, Seguridad y Gobernanza

> **Capas de Defensa en Profundidad:** Modelo de seguridad en anillos que incluye: Física, Identidad, Perímetro, Red, Procesos, Aplicación y Datos. Ninguna capa debe depender completamente de las demás.

### Microsoft Entra ID (antes Azure AD)
* **Gestión Principal:** Servicio de administración de identidades y acceso en la nube.
* **MFA:** Autenticación multifactor (algo que sabes, algo que tienes, algo que eres).
* **SSO:** Inicio de sesión único para múltiples aplicaciones con una sola cuenta.
* **RBAC:** Control de acceso basado en roles (otorga solo los permisos exactos necesarios).

### Herramientas de Gobernanza y Monitoreo
* **Azure Policy:** Crea y asigna reglas que controlan los recursos (ej. "solo crear VMs en cierta región").
* **Microsoft Defender for Cloud:** Protección unificada contra amenazas en la nube.
* **Azure Monitor:** Recopila datos de telemetría (métricas y registros) para maximizar el rendimiento.
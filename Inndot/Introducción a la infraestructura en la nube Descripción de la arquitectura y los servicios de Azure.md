# ☁️ Microsoft Azure: Resumen de Estudio

## 1. Conceptos Básicos e Infraestructura
Azure es un conjunto de servicios en la nube que ofrece libertad para crear, administrar e implementar aplicaciones en una red global.

### Modelos de Nube y Economía
* **Nube Pública:** Servicios ofrecidos a través de internet público y compartidos entre varias organizaciones.
* **Nube Privada:** Uso exclusivo de recursos en la nube por parte de una sola empresa.
* **Nube Híbrida:** Combina infraestructura local (on-premises) con la nube pública.
* **CapEx vs OpEx:** Azure funciona bajo un modelo de gastos operativos (**OpEx**), donde pagas por lo que consumes (modelo basado en el consumo), en lugar de gastos de capital (**CapEx**) que implica comprar hardware físico por adelantado.

### Jerarquía de Organización
* **Grupo de Administración:** El nivel más alto para gestionar recursos de forma masiva (políticas y accesos).
* **Suscripciones:** Proporcionan acceso autenticado y autorizado.
    * **Límite de facturación:** Determina cómo se genera la factura de la cuenta.
    * **Límite de control de acceso:** Administra el acceso a los recursos que los usuarios aprovisionan.
* **Grupos de Recursos:** Agrupaciones lógicas de recursos de Azure (un recurso solo puede estar en un grupo a la vez).
* **Recursos:** El bloque de creación básico (VM, bases de datos, etc.).

### Resiliencia Física
* **Regiones:** Áreas geográficas del planeta que contienen al menos tres zonas de disponibilidad.
* **Pares de Regiones (Region Pairs):** Cada región de Azure se empareja con otra dentro de la misma zona geográfica (a unos 500 km) para garantizar la recuperación ante desastres.
* **Zonas de Disponibilidad:** Centros de datos físicamente separados dentro de una región.
* **Conectividad:** Están conectadas a través de redes de fibra óptica de alta velocidad propias de Microsoft.

---

## 2. Servicios de Cómputo (Compute)

### Máquinas Virtuales (VM) - IaaS
* **Uso:** Ideal cuando se requiere control total sobre el SO y capacidad de ejecutar software personalizado.
* **Lift-and-Shift:** Excelente opción para mover servidores locales a la nube directamente sin rediseñar la aplicación.
* **Azure Virtual Desktop (AVD):** Permite ejecutar escritorios y aplicaciones de Windows en la nube desde cualquier dispositivo.
* **Alta Disponibilidad:**
    * **Dominio de actualización:** Agrupa máquinas que pueden reiniciarse al mismo tiempo durante mantenimientos (evita que todas se apaguen a la vez).
    * **Dominio de error:** Agrupa VMs que comparten fuente de alimentación y switch de red común (protege contra fallos de hardware).

### PaaS, Contenedores y Serverless
* **Azure App Service:** Servicio HTTP (PaaS) para hospedar aplicaciones web, API REST y backends para móviles sin gestionar la infraestructura.
* **Azure Container Instances (ACI):** La forma más rápida y sencilla de ejecutar un contenedor en Azure (PaaS), sin configurar servidores.
* **Azure Kubernetes Service (AKS):** Servicio de orquestación que administra el ciclo de vida, la escalabilidad y la actualización de los contenedores.
* **Azure Functions:** Código basado en eventos que escala según la demanda (arquitectura serverless).
    * **Sin estado:** Comportamiento por defecto donde se reinician en cada respuesta.
    * **Con estado (Durable Functions):** Permiten realizar seguimiento de la actividad y mantener el contexto a lo largo de varios pasos.

---

## 3. Redes y Conectividad

### Virtual Networks (VNet) y Equilibrio de Carga
* **VNet:** Permiten que los recursos de Azure se comuniquen entre sí, con internet y con redes locales.
* **Azure Load Balancer:** Distribuye el tráfico de red entrante entre varias máquinas virtuales para mejorar el rendimiento y la disponibilidad (Capa 4 - TCP/UDP).
* **Azure Application Gateway:** Equilibrador de carga de tráfico web que incluye un Firewall de aplicaciones web (WAF) (Capa 7 - HTTP/HTTPS).

### Comparativa de Conexión Híbrida
| Característica | VPN Gateway | ExpressRoute |
| :--- | :--- | :--- |
| **Tipo de Conexión** | Túnel cifrado a través de internet público. | Conexión privada dedicada de extremo a extremo. |
| **Seguridad** | Protege información confidencial evitando intercepciones. | Mayor seguridad al evitar la red pública de internet por completo. |
| **Rendimiento** | Depende del tráfico de internet. Ancho de banda limitado. | Velocidades de hasta 100 Gbps y latencias constantes y fiables. |

---

## 4. Almacenamiento (Azure Storage)

### Servicios Principales
1. **Blobs:** Almacenamiento de objetos masivos no estructurados (imágenes, documentos, backups).
2. **Files:** Recursos compartidos de archivos totalmente administrados accesibles mediante el protocolo SMB.
3. **Queues:** Servicio de mensajería para comunicación asíncrona entre componentes de aplicaciones.
4. **Disks:** Volúmenes a nivel de bloque administrados específicamente para máquinas virtuales.

### Niveles de Acceso (Access Tiers)
* **Frecuente (Hot):** Para datos a los que se accede de manera constante. Mayor costo de almacenamiento, menor costo de acceso.
* **Esporádico (Cool):** Para datos que se almacenan al menos 30 días y se acceden poco. 
* **Archivo (Archive):** Para datos que se almacenan al menos 180 días. Es la opción más barata de almacenamiento, pero la más cara y lenta para recuperar (puede tardar horas).

### Estrategias de Redundancia
* **LRS (Local):** 3 copias en un solo centro de datos. Es la opción más barata.
* **ZRS (Zonal):** 3 copias en zonas de disponibilidad (edificios) diferentes dentro de la misma región.
* **GRS (Geográfica):** Réplica asincrónica a una región secundaria distante (6 copias en total).
* **GZRS (Zonal-Geo):** La opción más resistente; hace ZRS en la región primaria y LRS en la secundaria.

---

## 5. Identidad, Seguridad y Gobernanza

### Microsoft Entra ID (antes Azure AD)
Servicio de administración de identidades y acceso basado en la nube.
* **MFA:** Autenticación multifactor para verificar identidades (algo que sabes, algo que tienes, algo que eres).
* **SSO:** Inicio de sesión único con una sola cuenta para múltiples aplicaciones.
* **RBAC (Control de acceso basado en roles):** Otorga a los usuarios solo los derechos y permisos exactos que necesitan para hacer su trabajo.

### Capas de Defensa en Profundidad
Modelo de seguridad en anillos que incluye: Física, Identidad y Acceso, Perímetro, Red, Procesos, Aplicación y Datos. Ninguna capa debe depender completamente de las demás.

### Herramientas de Gobernanza
* **Azure Policy:** Permite crear, asignar y administrar reglas que controlan o auditan los recursos (ej. "solo se pueden crear VMs en la región East US").
* **Microsoft Defender for Cloud:** Herramienta unificada de administración de la seguridad que proporciona protección contra amenazas en la nube.
* **Azure Monitor:** Recopila y analiza datos de telemetría (métricas y registros) de tus recursos en la nube y locales para maximizar su rendimiento.
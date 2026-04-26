---
tags: [Azure, Cloud, Gobernanza, Infraestructura, Apuntes]
fecha: 2026-04-26
título: Administración de infraestructura y gobernanza en Azure
---

# ☁️ Administración de infraestructura y gobernanza en Azure

## 💰 Factores que afectan los costos en Azure
Azure utiliza un modelo basado en el consumo (pago por uso), pero el precio final depende de una combinación de variables técnicas y logísticas:
* **Tipo de recurso:** Cada servicio tiene métricas de cobro distintas (ej. horas de VM vs GB almacenados en Blob Storage).
* **Geografía:** Azure está en todo el mundo, pero el costo de la electricidad y obra varía por región. Implementar una VM en "Brazil South" o "West US" puede tener un precio distinto.
* **Ancho de Banda (Transferencia de Datos):** Generalmente, los datos que entran a los centros de datos de Azure son gratuitos, pero los datos que salen (egress) tienen un costo basado en zonas de facturación.
* **Suscripciones y Marketplace:** Una suscripción de prueba gratuita incluye créditos iniciales, mientras que comprar software de terceros en el Azure Marketplace puede sumar cargos adicionales de proveedores externos.

### 📊 Estimación y control de costos
Para evitar "sorpresas" en la factura mensual, Azure proporciona herramientas para cada fase del proyecto:
* **Calculadora de precios:** Es una herramienta web para realizar estimaciones antes de implementar tu arquitectura. Te permite comparar niveles de servicio y costos entre regiones.
* **Microsoft Cost Management:** Es para el control durante el uso real. Permite visualizar el gasto mediante el análisis de costos, detectar picos inusuales y proyectar el gasto futuro.
* **Presupuestos y Alertas:** Puedes establecer límites de gasto. Al alcanzar un porcentaje (ej. 80%), el sistema envía alertas por correo. También existen alertas de crédito para cuotas por departamento.

### 🏷️ Propósito de las etiquetas (Tags)
Las etiquetas son metadatos (pares de Nombre:Valor) que se asignan a los recursos. Son la base de una buena gobernanza porque permiten:
* **Asignación de costos:** Agrupar recursos por "Centro de costos" o "Departamento".
* **Administración:** Identificar rápidamente quién es el "Dueño" del recurso o en qué "Entorno" (Desarrollo, Pruebas, Producción) reside.
* **Automatización:** Programar scripts que, por ejemplo, apaguen todas las VMs con la etiqueta `Entorno:Dev` los fines de semana para ahorrar dinero.
> [!warning] Nota
> Las etiquetas no se heredan automáticamente de un Grupo de Recursos al recurso; deben aplicarse individualmente o mediante Azure Policy.

---

## 📉 Opciones de optimización y Ahorro
Para reducir la factura de Azure, existen tres estrategias principales basadas en el tipo de carga de trabajo:
1. **Reservas (Reservations):** Ideales para cargas estables que estarán activas por mucho tiempo. Te comprometes a usar un recurso por 1 a 3 años a cambio de descuentos de hasta el 72%.
2. **Plan de Ahorro para cómputo:** Más flexible que las reservas. Te comprometes a un gasto fijo por hora en servicios de cómputo (VMs, App Service, etc.) durante 1 o 3 años. Azure aplica automáticamente el descuento al uso que más te convenga.
3. **Precios Spot:** Utiliza la capacidad sobrante de Azure a un precio muy bajo (hasta 90% de descuento). El riesgo es que Azure puede reclamar el recurso en cualquier momento con un aviso de 30 segundos. Es ideal para procesamiento por lotes (batch) o pruebas que pueden reiniciarse.
4. **Mantenimiento y Grupos de Recursos:** Al borrar una VM, a veces se olvidan los discos o las IPs públicas asociadas ("huérfanos"), los cuales siguen generando cargos. Organizar todo en Grupos de Recursos y usar el análisis de costos permite identificar estos elementos inactivos y optimizar.

---

## 🛡️ Gobernanza y Cumplimiento

### 🔍 Microsoft Purview: Gobernanza de Datos Unificada
Es la versión en la nube de la familia de soluciones diseñada para que las organizaciones tengan una visión clara y unificada de todos sus datos, sin importar si están en Azure, en otras nubes (como AWS) o en servidores locales. Su objetivo es gestionar el riesgo y el cumplimiento de la información confidencial.
* **Riesgo y Cumplimiento:** Utiliza herramientas para identificar datos sensibles en Microsoft 365 (como Teams o OneDrive) y protegerlos contra fugas o accesos no autorizados.
* **Gobernanza Unificada:** Crea un "mapa" de datos que incluye el linaje (de dónde vienen y a dónde van) y su clasificación automática. Esto permite que los analistas encuentren datos valiosos de forma segura y a escala.

### 📜 Azure Policy: El guardián de los estándares
Es el servicio que asegura que tus recursos cumplan con las normas de la organización. A diferencia de un simple permiso, una política evalúa la configuración del recurso y puede impedir que se creen elementos que no sigan las reglas.
* **Directivas e Iniciativas:** Una directiva es una regla individual (ej. "Solo crear VMs en la región de México"). Una iniciativa es un grupo de directivas relacionadas para cumplir un objetivo mayor (como cumplir un estándar de seguridad de 100 reglas).
* **Jerarquía y Herencia:** Las políticas se pueden aplicar a nivel de Suscripción o Grupo de Recursos y se heredan automáticamente hacia abajo.
* **Copilot:** La IA te asiste, pero Azure Policy actúa como un "límite de protección" que valida que las sugerencias de la IA respeten los SKUs y regiones permitidas.

### 🔒 Bloqueos de Recursos: Prevención de errores humanos
Incluso con los mejores permisos (RBAC), un administrador puede borrar una base de datos crítica por error. Los "Bloqueos de Recursos" son una capa de protección física que ignora los permisos del usuario hasta que el bloqueo se quita manualmente.
Existen dos tipos:
1. **Can Not Delete (Eliminar):** Los usuarios pueden leer y modificar el recurso, pero tienen prohibido borrarlo.
2. **Read Only (Solo lectura):** Los usuarios solo pueden ver el recurso. No pueden actualizarlo ni borrarlo (es el bloqueo más restrictivo).
> [!info] 
> Al igual que las políticas, los bloqueos se heredan. Si bloqueas un Grupo de Recursos, todos los elementos dentro quedan protegidos.

### 🏛️ Portal de Confianza de Servicios (Service Trust Portal)
Para las organizaciones que deben rendir cuentas ante auditores o leyes internacionales, este portal (https://servicetrust.microsoft.com) es la biblioteca pública de Microsoft sobre seguridad y privacidad.
* Los clientes pueden acceder a informes de auditoría independientes sobre los centros de datos de Microsoft.
* Detalles sobre cómo Microsoft implementa controles.
* Documentación técnica para ayudar a las empresas a cumplir normativas como GDPR, ISO, SOC.

---

## 🛠️ Herramientas de Interacción con Azure

Existen varias formas de gestionar los recursos, dependiendo de la tarea y tu nivel de experiencia:
* **Azure Portal:** Interfaz gráfica basada en web. Ideal para aprender, realizar configuraciones visuales rápidas y crear paneles de control personalizados. Altamente resistente (vive en todos los centros de datos).
* **Azure PowerShell:** Módulos para ejecutar comandos (cmdlets). Muy potente para administradores que conocen Windows y desean automatizar tareas mediante scripts repetibles.
* **Azure CLI:** Equivalente a PowerShell pero con sintaxis basada en Bash. Favorita de desarrolladores en entornos Linux o macOS.
* **Azure Cloud Shell:** Terminal accesible desde el navegador, preconfigurada con CLI y PowerShell. No requiere instalación local e incluye un editor de código integrado.
* **Copilot en Azure:** Asistente de IA que ayuda a redactar scripts, explicar configuraciones y acelerar operaciones mediante lenguaje natural.

---

## 🧠 Azure Resource Manager (ARM): El cerebro de la gestión

Cada vez que usas el Portal, la CLI o PowerShell, tu solicitud pasa por ARM. Es el servicio central de implementación y administración. Sus beneficios son:
* **Capa de gestión unificada:** Asegura que los resultados sean coherentes sin importar la herramienta que uses.
* **Seguridad:** Aplica de forma nativa el control de acceso basado en roles (RBAC).
* **Organización:** Permite gestionar recursos como grupo en lugar de piezas individuales y aplicar etiquetas para rastrear costos.

### 🏗️ Infraestructura como Código (IaC): Plantillas ARM y Bicep
Garantizan que las implementaciones de hardware virtual mediante archivos de texto sean idénticas en desarrollo y producción.
* **Plantillas ARM (JSON):** Utilizan sintaxis declarativa. Tú describes el *qué* (estado final) y Azure decide el *cómo*. Son idempotentes (puedes ejecutarlas múltiples veces sin causar errores).
* **Bicep:** Evolución de las plantillas JSON. Ofrece una sintaxis mucho más limpia, legible y fácil de escribir, manteniendo las ventajas de orquestación de ARM. Es el lenguaje recomendado por Microsoft para nuevos proyectos.

---

## 🌍 Extensión y Monitoreo de la Nube

### 🔗 Azure Arc
En el mundo real, no todo vive en Azure. Muchas empresas tienen servidores propios o en otras nubes. Azure Arc permite proyectar esos recursos externos dentro de Azure Resource Manager.
* **Gestión Centralizada:** Ver y administrar servidores Linux/Windows, clústeres de Kubernetes y bases de datos SQL que están fuera de Azure como si fueran recursos locales de la plataforma.
* **Cumplimiento:** Aplicar políticas de seguridad (Azure Policies).
* **DevOps:** Usar prácticas modernas de despliegue en entornos híbridos.

### 💡 Azure Advisor
Servicio gratuito que analiza la configuración y el uso de tus recursos para ofrecerte recomendaciones basadas en las mejores prácticas de Microsoft. Es como un arquitecto revisando tu trabajo 24/7. Las recomendaciones se agrupan en 5 pilares:
1. **Confiabilidad:** Alta disponibilidad en tus apps.
2. **Seguridad:** Mitigación de vulnerabilidades (basado en Defender for Cloud).
3. **Rendimiento:** Acelerar aplicaciones y bases de datos.
4. **Excelencia Operativa:** Eficiencia de flujos de trabajo.
5. **Costo:** Identificar recursos inactivos para ahorrar dinero.

### 🩺 Azure Service Health
El monitor de incidencias de la infraestructura de Microsoft. Te avisa cuando el problema no es tuyo. Tiene tres niveles:
1. **Estado de Azure (Azure status):** Informe global y público de la salud de todos los servicios en todas las regiones (para caídas masivas).
2. **Service Health:** Panel personalizado que muestra incidencias y mantenimientos de los servicios que *tú* estás usando.
3. **Resource Health:** Diagnóstico a nivel de recurso individual (ej. "Tu VM tiene errores de conectividad").

### 📈 Azure Monitor
La plataforma central para recopilar telemetría de todas partes (aplicaciones, SO, infraestructura) y analizarla para tomar decisiones automáticas.
* **Métricas y Registros (Logs):** Las métricas son valores numéricos en el tiempo (ej. % de CPU). Los registros son datos textuales con marca de tiempo (logs de errores).
* **Azure Log Analytics:** El buscador de tus logs. Utiliza KQL (Kusto Query Language) para buscar patrones entre millones de líneas de código.
* **Application Insights:** Enfocado en desarrolladores. Monitorea errores de código, tiempos de carga de la web y comportamiento de usuarios en la aplicación.
* **Alertas y Grupos de Acción:** Automatizan respuestas. Si la RAM llega al 90% (Alerta), el sistema puede enviar un aviso o ejecutar un script (Grupo de Acción).
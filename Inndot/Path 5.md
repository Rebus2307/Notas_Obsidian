# ☁️ AZ-104: Requisitos previos para administradores de Azure

## 💻 ¿Qué es Azure Cloud Shell?
Azure Cloud Shell es una terminal interactiva accesible mediante el explorador web para administrar recursos.
* 🔄 **Diferencia con CLI local:** Microsoft se encarga de mantener la versión más reciente de todos los módulos.
* 🌍 **Accesibilidad:** Es ideal para situaciones de emergencia o movilidad, ya que permite acceder a toda la infraestructura desde cualquier dispositivo (laptop personal, tablet o incluso smartphone) simplemente iniciando sesión en el Portal de Azure.
* ⚡ **Sin instalación:** No requiere instalación en tu computadora y las herramientas siempre están actualizadas.

## ⚙️ Funcionamiento y Persistencia
Cuando inicias Cloud Shell, se asigna temporalmente una máquina virtual.
* 💾 **Almacenamiento persistente:** Para que no pierdas tus scripts después de cerrar la sesión, Cloud Shell requiere montar un Azure File Share (recurso compartido de archivos). Todos los archivos se guardan en tu carpeta Home.
* 📝 **Editor Integrado:** Incluye un editor gráfico (basado en Code) que facilita la edición de scripts. Se puede invocar con el comando `code` directamente desde el navegador.
* 🔒 **Seguridad:** El entorno es seguro, repasa por cifrado doble y se vincula estrictamente a tus permisos de cuenta.

## 🛠️ Herramientas y Complementos Incluidos
Cloud Shell viene cargado con un ecosistema completo para desarrolladores e ingenieros de DevOps:

| Categoría | Herramientas disponibles |
| :--- | :--- |
| **Intérpretes** | Bash, PowerShell, Zsh, Python. |
| **Editores** | Editor de Cloud Shell (code), Vim, Nano, Emacs. |
| **Contenedores** | Docker, kubectl, Helm. |
| **Bases de datos** | Clientes para MySQL, PostgreSQL y SQL Server (sqlcmd). |
| **Infraestructura como código** | Terraform, Ansible, Chef, Puppet, Packer. |
| **Build & Dev** | Git, Make, Maven, npm, Pip. |

---

## ⚖️ ¿Cuándo usar (y cuándo no) Cloud Shell?

### ✅ Escenarios Ideales
* **Administración desde cualquier lugar:** Cuando no tienes tu equipo de trabajo y necesitas corregir algo.
* **Pruebas rápidas:** Ejecutar comandos de la CLI de Azure o revisar variables de entorno.
* **Automatización ligera:** Ejecutar scripts guardados en tu almacenamiento en la nube.

### ❌ Limitaciones
* **Tiempo de inactividad:** Las sesiones se desconectan tras 20 minutos de inactividad, perdiendo cualquier proceso que no se haya completado. No es para tareas de larga duración.
* **Permisos limitados:** Al ser un entorno administrado por Microsoft, no tienes acceso de administrador (root). No puedes instalar herramientas que requieran cambios profundos en el sistema operativo.
* **Sesión Única:** Solo se permite una sesión a la vez.

---

## 🏗️ La Infraestructura como Código (IaC)
La IaC es la práctica de describir la infraestructura necesaria para servidores, redes y bases de datos mediante archivos de definición o código.
* 🛡️ **Consistente:** Evita el error humano al configurar manualmente en el portal.
* 🔍 **Rastreable:** Puedes usar git para ver quién cambió qué.
* 🔄 **Idempotente:** Puedes ejecutar la misma plantilla 100 veces y el resultado siempre será el mismo estado.

### 📄 Estructura de una plantilla ARM (JSON)
La sintaxis de una plantilla ARM es declarativa. Tú declaras "necesito una máquina virtual" y Azure se encarga del "cómo" crearla.

**Elementos principales del archivo:**
* `$schema`: Define la ubicación del archivo de validación de Azure.
* `parameters`: Valores que cambian entre despliegues (ej. elegir entre un entorno de "Desarrollo" o "Producción").
* `variables`: Valores internos para simplificar la plantilla (ej. concatenar nombres de recursos).
* `resources`: La sección más importante. Aquí defines los componentes de Azure a crear (Storage, VMs, Redes).
* `outputs`: Datos que Azure devuelve tras terminar, como la dirección IP pública asignada.

---

## 🎛️ Añadiendo Flexibilidad: Parámetros y Salidas
Codificar valores de forma rígida (hardcoding) hace que las plantillas no sean reutilizables. Los parámetros permiten definir esto al momento del despliegue.

* 🔡 **Tipos:** `string`, `int`, `bool`, y `securestring` o `secureObject` (para contraseñas y secretos críticos que no deben quedar registrados).
* 🚫 **Restricciones:** Puedes usar `allowedValues` para limitar las opciones del parámetro (ej. limitar los tamaños de VM a los más económicos).

### 🧩 Funciones Útiles para Automatizar Datos
Dentro de la plantilla, usamos funciones para obtener datos en tiempo real:
* `[parameters('nombre')]`: Para llamar a un parámetro.
* `[resourceGroup().location]`: Para que el recurso se cree en la misma región que el grupo de recursos padre.
* `[reference(ID)]`: Para obtener datos de un recurso ya creado (como su URL de conexión).

---

## 🚀 Despliegue de Plantillas
Existen tres formas principales de desplegar estas plantillas en el mundo real:
1. **Local (CLI / PowerShell):** Ideal para pruebas rápidas usando comandos Bash.
2. **Plantillas Vinculadas:** Para proyectos gigantes, separando archivos distintos (ej. separar la red de la base de datos) en una "plantilla maestra".
3. **Canalizaciones CI/CD:** Integración con GitHub Actions o Azure Pipelines para hacer que la infraestructura se actualice automáticamente al hacer un *push* al repositorio.

### 🔄 Concepto de Idempotencia (Vital)
Es importante recordar que si ejecutas una plantilla, luego haces un pequeño cambio (como aumentar la RAM de una VM) y la vuelves a ejecutar, Azure **no borrará todo para empezar de cero**. Solo aplicará ese cambio específico, lo que garantiza una alta disponibilidad de producción.
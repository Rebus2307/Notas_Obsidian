---
tags: [M365, Desarrollo, Teams, Office-Addins, Apuntes]
fecha: 2026-04-26
título: Extender la experiencia de Microsoft 365
---

# 🌐 Extender la experiencia de Microsoft 365: Conceptos Básicos

## ✉️ ¿Qué son los Mensajes Accionables (Adaptive Cards)?
Los correos electrónicos pueden contener tarjetas adaptables (**Adaptive Cards**). En lugar de que el usuario lea un texto plano o haga clic en un enlace que lo lleve a la web, la tarjeta le permite interactuar directamente desde su bandeja de entrada.

**📋 Ejemplos comunes:**
- **Aprobaciones:** Aprobar un reporte de gastos o solicitud de vacaciones.
- **Encuestas:** Responder a un sondeo con un solo clic.
- **Sistema de Tickets:** Asignar o cerrar un ticket de soporte agregando notas.

### ⚙️ Componentes Técnicos
Para que esto funcione, se necesitan dos piezas de software:
1. **El Emisor:** Servicio que envía el email con la tarjeta incrustada en el HTML. El JSON de la tarjeta se inserta en una etiqueta `<script>` en el `<head>`.
2. **El Receptor (API Web):** Un endpoint HTTPS que tú desarrollas para recibir los datos cuando el usuario interactúa.

> [!example] Ejemplo de Estructura JSON
> ```json
> {
>   "type": "AdaptiveCard",
>   "originator": "ID-DE-PROVEEDOR",
>   "hideOriginalBody": "true",
>   "body": [ { "type": "TextBlock", "text": "Hola Wilfrido, ¿apruebas esto?" } ],
>   "actions": [ { "type": "Action.Http", "title": "Aprobar", "url": "[https://api.tu-escuela.edu/aprobar](https://api.tu-escuela.edu/aprobar)" } ]
> }
> ```

### ⚡ Tipos de Acciones en Outlook
- `Action.Http`: Envía información a tu servidor vía POST.
- `Action.InvokeAddInCommand`: Abre un complemento de Outlook.
- `Action.DisplayMessageForm`: Abre un formulario de correo o cita.
- `Action.ToggleVisibility`: Muestra u oculta elementos dinámicamente.

---

## 🔒 Registro y Seguridad

### 🌍 Ámbitos de Envío (Scopes)
Es necesario registrarse en el **Panel del Desarrollador** y definir quién recibirá los correos:
- **Usuarios de prueba:** Solo tú.
- **Organización:** Cualquier usuario de tu empresa (ej. dominio IPN/ESCOM). Requiere aprobación del administrador.
- **Global:** Para proveedores de software (ISV). Requiere verificación estricta de Microsoft.

### 🛡️ Requisitos de Seguridad
- **SPF y DKIM:** El correo debe estar autenticado para demostrar que no es suplantación.
- **Token de Portador (JWT):** Tu API debe validar el token enviado por Microsoft para confirmar la identidad del usuario que hizo clic.

---

## 🤝 Desarrollo de Aplicaciones en Microsoft Teams

### 🧩 Composición de la App
1. **Paquete de la app:** Un `.zip` con el manifiesto (JSON) e iconos.
2. **Servicios Web:** La lógica que hospedas en la nube (ej. Azure).
3. **Cliente de Teams:** Donde ocurre la interacción.

### 📍 Puntos de Extensibilidad
- **Pestañas (Tabs):** Páginas web (iframes) personales o grupales.
- **Bots de Conversación:** Procesan lenguaje natural en chats o canales.
- **Extensiones de Mensajería:** Permiten buscar datos externos e insertarlos como tarjetas en un chat.
- **Webhooks y Conectores:** Para enviar notificaciones externas hacia Teams.
- **Aplicaciones de Reuniones:** Experiencias antes, durante o después de videollamadas.

### 🎨 Elementos de Interfaz
- **Adaptive Cards:** Bloques de UI definidos en JSON.
- **Módulos de Tareas (Task Modules):** Ventanas emergentes para formularios o videos.
- **Deep Links:** URLs para navegar a partes específicas de Teams.

---

## 📄 Complementos de Office (Office Add-ins)

### 🤔 ¿Qué es un complemento?
Es una aplicación web que interactúa con el documento de Office pero vive fuera de él. Se define mediante un **archivo de manifiesto (XML)**.

**📂 Tipos principales:**
- **Panel de Tareas (Task Pane):** Barra lateral interactiva.
- **Contenido (Content):** Objetos insertados directamente en el documento (ej. gráficos).
- **Funciones Personalizadas:** Crear tus propias fórmulas en Excel usando JS/TS.

### 💻 Modelo de Programación (Office.js)
Se basa en llamadas asíncronas para no bloquear la app:
1. `load()`: Especificas qué datos del documento necesitas.
2. `context.sync()`: Sincronizas tu código con el documento real.

### ✨ Personalización Avanzada
- **Fluent UI:** Seguir el diseño oficial de Microsoft para que la app se vea nativa.
- **Microsoft Graph:** Conectar con la identidad del usuario para leer correos, archivos de OneDrive o calendario.

### 🛠️ Herramientas Esenciales
- **Yeoman Generator (`yo office`):** Para crear la estructura del proyecto rápidamente.
- **Script Lab:** Para probar código rápido (snippets) sin crear un proyecto.
- **npm run validate:** Comando obligatorio para revisar el manifiesto XML antes de publicarlo.

---

## 🚀 Implementación
1. **Sideloading:** Carga local para pruebas.
2. **Centralizada:** El administrador de TI lo instala a todos desde el panel de M365.
3. **AppSource:** Tienda pública mundial.
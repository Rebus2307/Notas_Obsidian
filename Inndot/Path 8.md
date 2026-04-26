---
tags: [Microsoft-Entra, Azure-AD, Identidad, Seguridad, Apuntes]
fecha: 2026-04-26
título: Introducción a Microsoft Entra
---

# 🛡️ Introducción a Microsoft Entra

## 🌐 La Familia Microsoft Entra
Microsoft Entra es una suite que unifica la identidad y el acceso a la red bajo el modelo de Confianza Cero.

**Componentes clave:**
- **Microsoft Entra ID:** El servicio principal (antes Azure AD).
- **Gobernanza de Identidades:** Automatiza el ciclo de vida de los usuarios.
- **Identificador externo:** Gestiona el acceso de clientes y socios externos.
- **Internet y Private Access:** Protege el tráfico hacia la web y aplicaciones locales sin VPNs tradicionales.

---

## 👤 Tipos de Identidades en Entra ID
- **Identidades Humanas:** Personas con cuenta (Miembros o Invitados).
- **Identidades de Cargas de Trabajo:** Para software (apps, contenedores). Se prefieren las **Identidades Administradas** porque Azure gestiona las credenciales automáticamente.
- **Identidades de Dispositivo:** Hardware unido a la organización o registrado (BYOD).
- **Identidades de Agente e IA:** Entidades que toman decisiones dinámicas.

> [!info] Identidad Híbrida
> **Entra Cloud Sync** sincroniza usuarios desde servidores locales (Active Directory) hacia la nube usando el estándar SCIM.

---

## 🔐 Autenticación y Seguridad

### 📱 Métodos de Autenticación
- **OATH (TOTP):** Códigos temporales vía Microsoft Authenticator.
- **Authenticator Lite:** MFA integrado en apps como Outlook.
- **Pase de Acceso Temporal (TAP):** Código de un solo uso para registros iniciales.

### ✨ Autenticación Sin Contraseña (Passwordless)
- **Windows Hello para empresas:** Biometría y chip TPM.
- **Claves de paso (FIDO2):** Criptografía de clave pública resistente al phishing.

### 🛡️ Acceso Condicional
Permite aplicar políticas de seguridad basadas en el contexto (ej. pedir MFA solo si la conexión es desde una red desconocida fuera de la escuela).

---

## 🚫 Protección de Contraseñas
- **Lista global de prohibidas:** Bloquea contraseñas comunes hackeadas.
- **Listas personalizadas:** Evita términos locales (ej. "Escom2026").
- **SSPR:** Autoservicio para que el usuario recupere su clave sin soporte técnico.

---

## 🚀 Gobernanza y Privilegio Mínimo
- **PIM (Privileged Identity Management):** Acceso Just-In-Time (JIT); permisos temporales y justificados para administradores.
- **RBAC:** Roles para controlar "quién" accede y a "qué" recursos.
- **Verified ID:** Credenciales descentralizadas para combatir deepfakes y asegurar identidades reales.
# 🛡️ Conceptos de Seguridad, Cumplimiento e Identidad

## 🤝 Modelo de Responsabilidad Compartida
Cuando una organización se mueve a la nube, la seguridad deja de ser responsabilidad exclusiva del cliente. Dependiendo del servicio, Microsoft asume más o menos control:
* 🏗️ **IaaS (Infraestructura)**: Microsoft cuida el edificio y el hardware; tú cuidas el Sistema Operativo, las apps y los datos.
* 🛠️ **PaaS (Plataforma)**: Microsoft cuida el SO y el entorno de ejecución; tú cuidas el código y los datos.
* 📦 **SaaS (Software)**: Microsoft cuida casi todo; tú solo cuidas quién accede y los datos.
* ⚠️ **Regla de oro**: Sin importar el modelo (SaaS, PaaS o IaaS), el cliente **siempre** es responsable de proteger sus **Datos, Identidades y Dispositivos** (puntos de conexión).

---

## 🏰 Defensa en Profundidad y la Triada CIA
La defensa en profundidad es una estrategia que utiliza capas para ralentizar un ataque. Si una capa falla, la siguiente protege los datos.
* **Capas**: Física $\rightarrow$ Identidad $\rightarrow$ Perímetro $\rightarrow$ Red $\rightarrow$ Cómputo $\rightarrow$ Aplicación $\rightarrow$ Datos.

Toda esta seguridad busca proteger la **Triada CIA**:
1. 🤫 **Confidencialidad**: Solo las personas autorizadas necesitan ver los datos (Cifrado).
2. 🛡️ **Integridad**: Los datos no han sido alterados (Hash).
3. ⏱️ **Disponibilidad**: Los datos están listos cuando se necesitan (Redundancia).

---

## 🚫 Modelo de Confianza Cero (Zero Trust)
Es el estándar moderno de seguridad. Su lema es *"Nunca confíes, siempre verifica"*. Se basa en tres principios:
1. 🔍 **Verificar explícitamente**: Validar siempre identidad, ubicación y estado del dispositivo.
2. 📉 **Privilegio mínimo**: Dar el acceso justo y necesario por el tiempo mínimo (JIT, JEA).
3. 🚨 **Asumir la brecha**: Trabajar como si el atacante ya estuviera dentro de la red.

* **Los 6 pilares de Zero Trust**: Identidad, Dispositivos, Aplicaciones, Datos, Infraestructura y Redes.

---

## 🔐 Cifrado vs Hash
Son herramientas matemáticas fundamentales para la seguridad de la información.

* **Cifrado (Protege Confidencialidad)**: Convierte datos legibles en ilegibles. Se cifran datos en reposo (disco), en tránsito (red/HTTPS) y en uso (en memoria RAM/enclaves).
    * *Simétrico*: La misma llave para cifrar y descifrar.
    * *Asimétrico*: Una llave pública (para cifrar) y una privada (para descifrar).
* **Hash (Protege Integridad)**: Convierte texto en una huella digital única de longitud fija. No se puede revertir. Si cambias una sola letra del archivo, el hash cambia por completo. Se usa para verificar que un archivo no fue alterado o para almacenar contraseñas de forma segura (añadiendo un valor aleatorio para evitar ataques de diccionario).

---

## 🏛️ Gobernanza, Riesgo y Cumplimiento (GRC)
* 📜 **Gobernanza**: El sistema de políticas para dirigir la organización (¿quién tiene permisos de Admin?).
* ⚠️ **Riesgo**: Identificar qué puede salir mal (externo como ataques, o interno como fraude).
* ✅ **Cumplimiento Normativo**: Acatar las leyes (como el GDPR en Europa o leyes locales).

### Conceptos clave de Datos
* 📍 **Residencia de datos**: Dónde viven físicamente los servidores.
* ⚖️ **Soberanía de datos**: Qué leyes nacionales aplican a esos datos por estar ahí.
* 👁️ **Privacidad**: Transparencia sobre cómo usas los datos personales.

---

## 🛂 Autenticación vs Autorización (AuthN vs AuthZ)
Aunque suenan similar, cumplen funciones distintas.

* 🆔 **Autenticación (AuthN)**: ¿Eres quien dices ser? Es el proceso de verificar tu identidad mediante credenciales (contraseñas, biometría, tokens).
* 🔑 **Autorización (AuthZ)**: ¿Qué tienes permitido hacer? Una vez autenticado, el sistema revisa tus permisos (roles) para decidir si puedes leer un archivo, borrar datos, etc.

> 🏨 **La analogía del hotel**: Presentar tu identificación en recepción para que te den una llave es **Autenticación**. Que esa llave abra tu habitación, pero no la suite presidencial o el gimnasio, es **Autorización**.

---

## 📱 MFA y Autenticación sin Contraseña
Las contraseñas son el eslabón más débil. Por ello, la industria se mueve hacia:
* 🛡️ **MFA (Autenticación Multifactor)**: Requiere al menos dos factores de categorías distintas:
    1. *Algo que sabes*: Contraseña o PIN.
    2. *Algo que tienes*: Tu teléfono (Microsoft Authenticator) o llave física (Yubikey).
    3. *Algo que eres*: Huella digital o reconocimiento facial (Windows Hello).
* 🚫 **Sin Contraseña (Passwordless)**: Elimina el riesgo de robo de contraseñas usando certificados digitales, biometría o llaves FIDO2.

---

## 🌐 Nuevo Perímetro de Seguridad
En el pasado, la seguridad era como un castillo: un muro fuerte (Firewall/VPN) protegía todo lo que estaba dentro.
* 🧱 **Perímetro Tradicional**: Basado en la ubicación física (estar dentro de la red de la oficina).
* 👤 **Perímetro Moderno (Identidad)**: Con el trabajo remoto y la nube, los datos están fuera del muro. No importa desde dónde te conectes o qué red uses; lo único que importa es **quién eres** y si tu dispositivo es seguro. La identidad es el factor común en todas las conexiones.

---

## 🔑 Proveedores de Identidad (IdP), SSO y Directorios

* **Proveedor de Identidad (IdP)**: Un servicio central que gestiona las cuentas. En lugar de que cada aplicación (Facebook, Spotify, Azure) guarde tu contraseña, ellas confían en el IdP.
* **Tokens de Seguridad**: Tras autenticarte, el IdP emite un "ticket" digital (SAML o JWT) que le dice a la aplicación que eres tú, sin que esta guarde tu contraseña.
* **SSO (Single Sign-On)**: Inicias sesión una vez en el IdP y accedes a todas las aplicaciones sin volver a escribir la contraseña. Mejora la experiencia y reduce ataques de phishing.
* **Protocolos estándar**: OIDC (Autenticación), OAuth 2.0 (Autorización) y SAML (Empresas/Legacy).

### Servicios de Directorio: AD DS vs Microsoft Entra ID
Un servicio de directorio es la base de datos donde viven los objetos de la red (usuarios, grupos, impresoras).
* 🏢 **Active Directory Domain Services (AD DS)**: El estándar local (On-premise). Diseñado para redes físicas, impresoras y protocolos antiguos como Kerberos.
* ☁️ **Microsoft Entra ID (antes Azure AD)**: El estándar de la nube. Diseñado para internet, aplicaciones móviles y protocolos modernos (OAuth/SAML). No usa jerarquía de "bosques y árboles" física, es un modelo de Identidad como Servicio (IDaaS).

---

## 🤝 Federación: El "Pasaporte" Digital
La federación permite que uses tu cuenta de la Organización A para entrar a recursos de la Organización B, sin crear una cuenta nueva.
* **Confianza**: La Organización B confía en que si la Organización A dice que eres tú, es verdad.
* **B2B**: Útil para colaborar con proveedores externos.
* **Identidades Sociales**: Cuando entras a un sitio de terceros con tu cuenta de Google o GitHub, estás usando Federación.
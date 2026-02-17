---
tags:
  - AZ-900
  - MicrosoftAzure
  - CloudComputing
  - Certificación
fecha: 2026-02-16
---
# Fundamentos de la Infraestructura en la Nube: AZ-900

## 📊 Descripción del Examen
La distribución del contenido para la certificación es la siguiente:
* **Conceptos de la nube:** 25-30%
* **Arquitectura y servicios de Azure:** 35-40%
* **Administración y gobernanza de Azure:** 30-35%

---

## ☁️ ¿Qué es la Informática en la Nube?
Es la prestación de servicios informáticos a través de Internet, permitiendo desde infraestructuras simples hasta soluciones complejas.
* **Infraestructura de TI:** Máquinas virtuales (VMs), almacenamiento, bases de datos y redes.
* **Servicios Avanzados:** IoT (Internet de las cosas), ML (Aprendizaje Automático) e IA (Inteligencia Artificial).

### Modelos de Implementación
1. **Nube Privada:** Utilizada por una sola entidad. Ofrece mayor control pero requiere inversión en hardware y mantenimiento.
2. **Nube Pública:** Propiedad de un proveedor de servicios externo. Es accesible para cualquier persona y no requiere gastos de capital iniciales para escalar.
3. **Nube Híbrida:** Un entorno que combina nubes públicas y privadas, permitiendo que los datos y aplicaciones se compartan entre ellas para máxima flexibilidad.

---

## 🤝 Modelo de Responsabilidad Compartida
Divide las tareas de seguridad y gestión entre el proveedor de la nube y el cliente.

* **Responsabilidad del Cliente:** Siempre es responsable de la información, los datos, los dispositivos móviles/terminales, y las cuentas e identidades.
* **Responsabilidad del Proveedor:** Seguridad física del centro de datos, red física y hosts físicos.

---

## 💰 Modelo Basado en el Consumo
* **CapEx (Gastos de Capital):** Gasto de dinero en infraestructura física por adelantado (ej. comprar un servidor).
* **OpEx (Gastos Operativos):** Gastos continuos por el uso de servicios o productos. La nube es un modelo OpEx.
* **Beneficios:** Sin costos de infraestructura iniciales y pago exclusivo por lo que se utiliza.

---

## 🚀 Ventajas de la Nube
* **Alta Disponibilidad:** Garantiza que las aplicaciones estén en funcionamiento sin importar interrupciones.
* **Escalabilidad:** Capacidad de ajustar los recursos según la demanda.
    * **Vertical:** Aumento de potencia (CPU/RAM) a una instancia existente.
    * **Horizontal:** Añadir más instancias (VMs o contenedores).
* **Fiabilidad:** Gracias a su escala global, la nube puede recuperarse rápidamente de fallos catastróficos.
* **Previsibilidad:** Permite predecir tanto el rendimiento como los costos operativos.

---

## 🛠️ Modelos de Servicio (IaaS, PaaS, SaaS)

| Modelo | Descripción | Perfil Ideal |
| :--- | :--- | :--- |
| **IaaS** | Infraestructura como servicio. Alquiler de hardware y red física. Tú gestionas el SO. | Administradores de IT |
| **PaaS** | Plataforma como servicio. Entorno de desarrollo listo sin gestionar servidores. | Desarrolladores |
| **SaaS** | Software como servicio. Aplicaciones listas para el usuario final vía web. | Usuarios Finales |

* **IaaS (Escenario):** Migración "Lift-and-shift" de servidores locales a la nube.
* **PaaS (Escenario):** Marcos de desarrollo, análisis o inteligencia empresarial.
* **SaaS (Escenario):** Email, Microsoft 365, Drive o aplicaciones de finanzas.
---
materia: IT Governance
unidad: "I - Modelos de Gobierno Corporativo y de Tecnología"
tags: [gobierno-ti, cobit, iso9001, iso38500]
proyecto: proyecto-gobierno-it.vercel.app
---

# Unidad I – Modelos de Gobierno Corporativo y de Tecnología

## 1. Enfoque basado en procesos (ISO 9001)

- **ISO 9001** = norma de **Sistemas de Gestión de Calidad (SGC)**.
- El **enfoque basado en procesos** propone gestionar la organización como una **red de procesos interrelacionados**, en lugar de como funciones aisladas.
- Este enfoque se apoya en el ciclo **PHVA / PDCA**:
  - **P**lanificar → **H**acer → **V**erificar → **A**ctuar
- Objetivo: lograr resultados consistentes y previsibles de forma más eficaz y eficiente.

> [!note] Relación con Gobierno de TI
> El enfoque de procesos es la base conceptual que luego retoman marcos como **COBIT 2019** e **ITIL V.4** para modelar sus propios catálogos de procesos.

---

## 2. Diagrama de la tortuga (Método de la Tortuga)

Herramienta visual para **analizar y documentar un proceso**, evaluando 6 elementos (la forma recuerda a una tortuga):

| Parte de la tortuga | Elemento del proceso | Pregunta clave |
|---|---|---|
| 🐢 Cabeza | **Entradas (inputs)** | ¿Qué recursos/información entran al proceso? |
| 🐢 Cuerpo | **Actividades** | ¿Qué se hace? (secuencia de actividades que transforman entradas en salidas) |
| 🐢 Pata 1 | **Recursos / materiales** | ¿Con qué? |
| 🐢 Pata 2 | **Personas** | ¿Con quién? (responsables, roles, competencias) |
| 🐢 Pata 3 | **Métodos / procedimientos** | ¿Cómo? (instrucciones de trabajo, normas aplicables) |
| 🐢 Pata 4 | **Indicadores / KPI's** | ¿Cuánto? (cómo se mide el desempeño del proceso) |
| 🐢 Cola | **Salidas (outputs)** | ¿Para qué? (resultado, producto o servicio entregado — el objetivo del proceso) |

**Puntos clave:**
- Todo proceso analizado con este método debe cerrar el ciclo con **retroalimentación**: los resultados (salidas + KPI's) se revisan y usan para ajustar el proceso — esto conecta directamente con el ciclo PHVA.
- ¿Cómo se garantiza que la gestión de un proceso sea adecuada? → **Aplicando indicadores o métricas (KPI's)** que permitan medir eficacia, eficiencia y cumplimiento de objetivos.

---

## 3. Gobierno Corporativo vs. Gobierno de TI

### Gobierno Corporativo
Sistema mediante el cual las organizaciones son **dirigidas y controladas**. Busca:
- Equilibrar los intereses de todos los **stakeholders** (accionistas, clientes, empleados, proveedores, reguladores, sociedad, etc.).
- Definir la estructura a través de la cual se establecen los objetivos de la empresa, los medios para alcanzarlos y la forma de monitorear el desempeño.

### Gobierno de TI (IT Governance)
Es un **subconjunto del gobierno corporativo**, enfocado específicamente en la tecnología de información. Busca asegurar que:
- TI esté **alineada** con los objetivos del negocio.
- TI **genere valor** para la organización.
- Los **riesgos** relacionados con TI se gestionen adecuadamente.
- Los **recursos de TI** (personas, infraestructura, información) se usen de forma responsable.

---

## 4. Roles clave: Stakeholders, Directors, Executive

| Rol | Descripción |
|---|---|
| **Stakeholders** | Público objetivo / partes interesadas en un sentido amplio: accionistas, clientes, empleados, proveedores, reguladores. Sus necesidades y expectativas son el punto de partida del gobierno. |
| **Directors** (Consejo Directivo / Board) | Responsables del **gobierno**: evalúan el uso actual y futuro de TI, dirigen la preparación e implementación de planes y políticas, y monitorean el cumplimiento y desempeño. |
| **Executive** (Dirección Ejecutiva / Management) | Responsables de la **gestión**: implementan y ejecutan los planes definidos por los directors, y reportan resultados hacia el gobierno. |

### Modelo Evaluar–Dirigir–Monitorear (EDM) — ISO 38500 / COBIT 2019

1. **Evaluar (Evaluate):** los *directors* evalúan el uso actual y futuro de TI, considerando presiones del negocio y necesidades de los stakeholders.
2. **Dirigir (Direct):** se asignan responsabilidades y se dirige la preparación e implementación de planes y políticas de TI.
3. **Monitorear (Monitor):** se supervisa el cumplimiento de las políticas y el desempeño de TI frente a los planes establecidos.

> [!important] Gobierno ≠ Gestión (distinción clave de COBIT 2019)
> - **Gobierno (Governance):** responsabilidad del órgano de gobierno (Board/Directors). Evalúa necesidades y opciones de los stakeholders, fija la dirección mediante priorización y toma de decisiones, y monitorea el desempeño frente a la dirección acordada → **EDM (Evaluar, Dirigir, Monitorear)**.
> - **Gestión (Management):** responsabilidad de la dirección ejecutiva. Planea, construye, ejecuta y monitorea actividades alineadas con la dirección fijada por el gobierno → dominios **APO, BAI, DSS, MEA** de COBIT 2019.

---

## 5. Dominios de COBIT 2019 (para referencia rápida)

| Dominio | Significado | Responsable |
|---|---|---|
| **EDM** | Evaluate, Direct, Monitor (Evaluar, Dirigir, Monitorear) | Gobierno (Directors) |
| **APO** | Align, Plan, Organize (Alinear, Planificar, Organizar) | Gestión |
| **BAI** | Build, Acquire, Implement (Construir, Adquirir, Implementar) | Gestión |
| **DSS** | Deliver, Service, Support (Entregar, Dar Servicio, Soportar) | Gestión |
| **MEA** | Monitor, Evaluate, Assess (Monitorear, Evaluar, Valorar) | Gestión |

---

## 6. Pendientes / por completar
- [ ] Cascada de metas COBIT 2019 (práctica 1)
- [ ] Mapa Estratégico (práctica 2)
- [ ] Caso de Negocio (práctica 3)
- [ ] Norma ISO 38500 a detalle
- [ ] Green IT: métricas de eficiencia energética y buenas prácticas

---
**Proyecto de referencia:** `proyecto-gobierno-it.vercel.app`
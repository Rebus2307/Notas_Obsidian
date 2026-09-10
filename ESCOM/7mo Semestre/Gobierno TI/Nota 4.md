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

## 6. Pirámide de marcos de Gobierno

La estructura de gobierno se organiza en capas, desde lo más estratégico hasta lo más operativo:

| Nivel | Marcos / Estándares |
|---|---|
| **Cumplimiento legal** | COSO |
| **Gobierno Corporativo / Gobierno de TI** | ISO 38500, COBIT / Val IT |
| **Estándares de mejores prácticas** | ISO 27000 |
| *(otros niveles relacionados, ver abajo)* | |

### Directrices que rigen los marcos
Todo marco de gobierno responde a dos tipos de directrices:

- **Desempeño (Performance):** orientadas a las **metas del negocio** — crecimiento, rentabilidad, valor generado.
- **Conformidad (Conformance):** orientadas al **cumplimiento normativo/legal**, por ejemplo:
  - **Basilea (Basel II/III)** — regulación financiera/bancaria (gestión de riesgo)
  - **Sarbanes-Oxley Act (SOX)** — control interno y reportes financieros (EUA)
  - **LOPD** (Ley Orgánica de Protección de Datos) — protección de datos personales
  - Otras regulaciones sectoriales, según el país/industria

### Marcos por nivel de gobierno

| Nivel de gobierno | Marcos asociados |
|---|---|
| **Gobierno Corporativo** | **Balanced Scorecard (BSC)**, **COSO** |
| **Gobierno de TI** | **ISO 38500**, **COBIT / Val IT** |
| **Estándares de mejores prácticas** | ISO 24762 (recuperación ante desastres), ISO 27000 (seguridad de la información), ISO 20000 (gestión de servicios de TI) — *en este curso trabajaremos con **ISO 22301** (continuidad de negocio)* |
| **Procesos y procedimientos** | Continuidad de negocio, principios de seguridad, **ITIL** |

> [!tip] Cómo leerlo
> El Gobierno Corporativo marca la dirección estratégica general (con BSC/COSO); el Gobierno de TI la traduce a nivel tecnológico (ISO 38500/COBIT); los estándares de mejores prácticas la operacionalizan (ISO 27000, 22301, 20000); y los procesos/procedimientos (ITIL, planes de continuidad) la ejecutan en el día a día.

---

## 7. COSO (Committee of Sponsoring Organizations)

### Definición de Gobierno Corporativo (enfoque COSO / ERM)
> Es un **proceso efectuado por el Consejo de Administración** de una entidad, su dirección y el resto del personal, **aplicado en la definición de estrategias** en toda la empresa y **diseñado para identificar eventos potenciales** que puedan afectar a la organización, **gestionar sus riesgos** dentro del riesgo aceptado (*risk appetite*) y **proporcionar una seguridad razonable** sobre el logro de los objetivos.

### Capacidades que aporta el Gobierno Corporativo (COSO ERM)
1. **Alinear** el riesgo aceptado (*risk appetite*) y la estrategia.
2. **Mejorar** las decisiones de respuesta a los riesgos.
3. **Reducir** las sorpresas y pérdidas operativas.
4. **Identificar y gestionar** la diversidad de riesgos para toda la entidad (riesgos cruzados entre áreas).
5. **Aprovechar** las oportunidades.
6. **Mejorar** la dotación (despliegue) de capital.

---

## 8. Balanced Scorecard (BSC) — Cuadro de Mando Integral

Herramienta de gestión estratégica (Kaplan & Norton) que traduce la estrategia en objetivos e indicadores organizados en **4 dimensiones (perspectivas)**:

| Dimensión | Enfoque |
|---|---|
| **Financiera** | Resultados económicos, rentabilidad, valor para accionistas |
| **Cliente / Usuario** | Propuesta de valor, satisfacción, retención |
| **Interna / Procesos** | Eficiencia y calidad de los procesos internos clave |
| **Aprendizaje y crecimiento** | Capital humano, información y organización (capacidades para innovar y mejorar) |

> [!important] Uso en el curso
> Estas 4 dimensiones son la base para elaborar el **Mapa Estratégico** (Práctica 2), donde se conectan objetivos de cada dimensión mediante relaciones causa-efecto, típicamente de abajo hacia arriba: Aprendizaje y crecimiento → Procesos internos → Cliente → Financiera.

---

## 10. Componentes del Gobierno Corporativo (Cubo COSO ERM)

El modelo COSO ERM se representa como un **cubo de 3 dimensiones**: categorías de objetivos, componentes y niveles organizacionales.

### a) Categorías de objetivos
| Categoría | Enfoque |
|---|---|
| **Estratégicos** | Metas de alto nivel, alineadas y en apoyo de la misión |
| **Operaciones** | Uso eficaz y eficiente de los recursos |
| **Informes (Reporting)** | Confiabilidad de la información reportada |
| **Cumplimiento** | Cumplimiento de leyes y normas aplicables |

### b) Los 8 componentes del proceso de gestión de riesgos
1. **Ambiente interno** — la cultura, filosofía de riesgo y el tono de la organización; base de todos los demás componentes.
2. **Establecimiento de objetivos** — deben existir antes de identificar eventos que puedan afectarlos; alineados con la misión y el riesgo aceptado.
3. **Identificación de eventos** — se detectan eventos internos y externos que afectan el logro de objetivos, en distintos niveles:
   - **Entidad** (toda la organización)
   - **División**
   - **Unidad de Negocio**
   - **Subsidiaria**
4. **Evaluación de riesgo** — se analizan los riesgos considerando probabilidad e impacto, como base para determinar cómo administrarlos.
5. **Respuesta al riesgo** — la dirección selecciona una respuesta (evitar, aceptar, reducir o compartir el riesgo).
6. **Actividades de control** — políticas y procedimientos que aseguran que las respuestas al riesgo se lleven a cabo efectivamente.
7. **Información y comunicación** — se identifica, captura y comunica la información relevante en tiempo y forma.
8. **Monitoreo** — se supervisa la totalidad del proceso y se realizan las modificaciones necesarias.

> [!note] Niveles organizacionales
> Los 8 componentes y las 4 categorías de objetivos se aplican en cascada a través de los niveles: **Entidad → División → Unidad de Negocio → Subsidiaria**.

### c) Roles responsables del Gobierno Corporativo
| Rol | Responsabilidad |
|---|---|
| **Consejo de Administración** | Supervisa la gestión, aprueba la estrategia y vigila que el riesgo se mantenga dentro del nivel aceptado |
| **Alta Gerencia** | Diseña e implementa el proceso de gestión de riesgos, responde ante el Consejo |
| **Auditoría Interna** | Brinda **aseguramiento** sobre la eficacia del proceso de gestión de riesgos, aportando **visión** y **objetividad** independiente |

---

## 11. Marcos de referencia — CMMI (Modelo de Capacidad y Madurez)

**CMMI (Capability Maturity Model Integration)**: modelo que describe niveles de madurez de los procesos de una organización, usado para evaluar y mejorar su capacidad de desarrollo/gestión.

| Nivel | Nombre | Característica |
|---|---|---|
| **1** | **Inicial** | Proceso impredecible, poco controlado y reactivo |
| **2** | **Gestionado** | Proceso caracterizado por proyectos: se planifica, ejecuta, mide y controla a nivel de proyecto |
| **3** | **Definido** | Proceso organizado: se caracteriza y comprende bien; se documenta con estándares, procedimientos y métodos a nivel de toda la organización |
| **4** | **Cuantitativamente gestionado** | Proceso medible y controlado mediante técnicas estadísticas y otras técnicas cuantitativas |
| **5** | **Optimizado** | Enfoque en la **mejora continua** del proceso, mediante innovación incremental y basada en datos |

> [!tip] Progresión
> Cada nivel se construye sobre el anterior: no se puede "saltar" niveles, ya que la madurez de gestión (nivel 2), organización (nivel 3) y medición (nivel 4) son prerrequisitos para poder optimizar (nivel 5).

---

## 12. Ciclo de Deming (PDCA)

Ciclo de **mejora continua**, base metodológica de muchos marcos de gobierno y calidad (incluido el enfoque de procesos de ISO 9001 visto antes):

- **P – Plan (Planificar):** definir objetivos y el proceso necesario para lograr los resultados esperados.
- **D – Do (Hacer):** implementar el plan, ejecutar el proceso.
- **C – Check (Verificar):** monitorear y medir los resultados frente a lo planificado.
- **A – Act (Actuar):** tomar acciones para mejorar continuamente el desempeño del proceso, con base en lo verificado.

Es un **ciclo iterativo**: al terminar "Actuar" se retroalimenta directamente a "Planificar", por lo que puede representarse comenzando desde cualquier punto (por ejemplo A → P → D → C), siempre y cuando se respete la secuencia lógica **Planificar → Hacer → Verificar → Actuar → (retroalimenta a Planificar)**.

> [!important] Relación con lo ya visto
> El PDCA es el "motor" detrás del **Monitoreo** (componente 8 del COSO ERM) y del salto al **Nivel 5 – Optimizado** de CMMI: ambos dependen de repetir este ciclo de forma constante.
## 13. ISO 38500 (International Standard)

Norma internacional que da lineamientos para el **Gobierno Corporativo de TIC**.

### Objetivos de la norma
1. **Generar confianza en los stakeholders** (empleados, clientes, proveedores, socios, accionistas, etc.) respecto al Gobierno Corporativo de TIC.
2. **Informar y guiar a la Alta Dirección** en el Gobierno de TIC dentro de su organización.
3. **Proveer las bases para la evaluación objetiva** del Gobierno Corporativo de TIC.

---

## 14. Gobierno de TI — Definición

> **Gobierno de TI:** proceso de administración que asegura la obtención de los beneficios esperados de la tecnología de información de manera controlada, para acrecentar el éxito de la empresa.

> Es el **uso eficiente de los recursos de TI** para apoyar el cumplimiento de los objetivos del negocio.

**Composición:**
$$\text{Alta Dirección} + \text{Área de TI} \;\longrightarrow\; \text{Procesos} + \text{Tecnología} + \text{Personas} = \text{Gobierno de TI}$$

### Beneficios de un buen Gobierno de TI
| Beneficio | Descripción |
|---|---|
| **Equipo** | Liderazgo alineado, con la mezcla exacta de habilidades para analizar la situación actual |
| **Apertura** | Disposición para escuchar, enfrentar los hechos y no buscar culpables |
| **Perspectiva empresarial** | Capacidad de ver la perspectiva completa (visión integral del negocio, no solo de TI) |
| **Análisis basado en hechos** | Información relevante y precisa que refleja la realidad, con evidencia cuantitativa y cualitativa |

---

## 15. Modelo de Gobierno de TI (ISO 38500 — ciclo Evaluar / Dirigir / Monitorear)

El modelo describe cómo el órgano de gobierno dirige y controla el uso de TI en la organización:

1. **Punto de partida:** presiones del negocio y necesidades del negocio.
2. **Evaluar:** el órgano de gobierno evalúa el **uso actual y futuro de TI**, considerando el desempeño, la conformidad, y las presiones/necesidades del negocio.
3. **Dirigir:** a partir de la evaluación, se emiten **planes y políticas** que marcan la dirección a seguir.
4. Esos planes y políticas se ejecutan en dos frentes:
   - **Proyectos** → cambios y posibilidades habilitadas por TI.
   - **Operaciones de TI** → operaciones del negocio habilitadas/soportadas por TI.
5. **Monitorear:** se supervisa el **desempeño** (¿se están logrando los objetivos?) y la **conformidad** (¿se cumplen políticas, normas y regulaciones?) tanto de los proyectos como de las operaciones.
6. El monitoreo retroalimenta al proceso de **Evaluar**, cerrando el ciclo continuo:

```
Presiones/Necesidades del negocio
            │
            ▼
        EVALUAR  ◄────────────────┐
            │                     │
            ▼                     │
        DIRIGIR                   │
   (Planes y Políticas)           │
            │                     │
   ┌────────┴────────┐            │
   ▼                  ▼           │
Proyectos        Operaciones IT   │
(Cambios /       (Operación del   │
posibilidades    negocio          │
por TI)          habilitada       │
                 por TI)          │
   │                  │           │
   └────────┬─────────┘           │
            ▼                     │
        MONITOREAR                │
   (Desempeño / Conformidad) ─────┘
```

> [!important] Conexión con lo ya visto
> Este es el mismo modelo **EDM (Evaluar–Dirigir–Monitorear)** que vimos con los roles de *Directors* y *Executive* — aquí se detalla el flujo completo: entradas (presiones/necesidades), salidas de dirección (planes/políticas), ejecución (proyectos/operaciones) y control (desempeño/conformidad).

---

## 16. Pendientes / por completar
- [ ] Cascada de metas COBIT 2019 (práctica 1)
- [x] Bases teóricas para Mapa Estratégico (BSC, dimensiones) — *revisado, falta elaborar el mapa* (práctica 2)
- [ ] Caso de Negocio (práctica 3)
- [x] Norma ISO 38500 a detalle
- [ ] Green IT: métricas de eficiencia energética y buenas prácticas
- [ ] Detalle de ISO 22301 (continuidad de negocio) — se usará en unidad V
- [ ] Relacionar CMMI con los procesos de COBIT 2019 (niveles de capacidad de proceso)

---
**Proyecto de referencia:** `proyecto-gobierno-it.vercel.app`
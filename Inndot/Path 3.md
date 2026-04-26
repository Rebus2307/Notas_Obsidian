# 🤖 Introducción a la Inteligencia Artificial: IA Generativa y Agentes

La IA Generativa es una rama de la IA que crea contenido nuevo (texto, imágenes, voz, código) basándose en modelos de lenguaje entrenados con grandes volúmenes de datos. Su base principal es el Procesamiento de Lenguaje Natural (NLP), lo que permite que la IA "entienda" el lenguaje y sus relaciones semánticas.

* 🎯 **Prompt**: Es la instrucción en lenguaje natural que se le da a la IA.
* 📚 **Modelos de Lenguaje**:
    * 🐋 **LLM (Grandes Modelos de Lenguaje)**: Eficaces y generales, pero costosos computacionalmente.
    * 🐟 **SLM (Pequeños Modelos de Lenguaje)**: Enfocados en áreas específicas, ideales para ejecutarse en dispositivos locales.
* 🛠️ **Casos de uso comunes de NLP**: Clasificación (categorizar documentos), Extracción (identificar entidades como nombres, fechas o lugares) y Resumen (reducir texto a los puntos principales).

### 🧠 Capacidades Cognitivas
* 🗣️ **Tecnologías de Voz (Speech)**: Permiten la interacción mediante el lenguaje hablado. Incluye el Reconocimiento de voz (Speech-to-text) y la Síntesis de voz (Text-to-speech) para transcripciones o traducción automática.
* 👁️ **Visión por Computadora (Computer Vision)**: Análisis de imágenes, videos y cámaras en vivo para Clasificación, Detección de objetos y Segmentación semántica (a nivel de píxeles).
* 📄 **Extracción de Información (OCR)**: Reconocimiento Óptico de Caracteres para procesar facturas, digitalizar archivos e indexar documentos no estructurados.

### ⚖️ IA Responsable (Los 6 Pilares)
Para que la IA sea ética, debe seguir principios fundamentales:
1. 🤝 **Equidad**: Evitar sesgos y discriminación.
2. 🛡️ **Confiabilidad y seguridad**: Mitigar errores en modelos probabilísticos.
3. 🔒 **Privacidad y seguridad**: Proteger los datos personales.
4. 🌍 **Inclusión**: Diseñar para que todos puedan usarla.
5. 🔍 **Transparencia**: Informar cómo funciona el sistema y sus limitaciones.
6. 📝 **Responsabilidad**: Rendición de cuentas por parte de las organizaciones creadoras.

---

## ⚙️ Fundamentos de Machine Learning y Deep Learning
La IA busca imitar la inteligencia humana, y para lograrlo utiliza Machine Learning (ML), un método basado en algoritmos y datos que encapsula una función matemática para predecir una etiqueta ($Y$) basándose en características de entrada ($X$).

* 🧑‍🏫 **Aprendizaje Supervisado**: Predicciones basadas en datos ya etiquetados.
    * 📈 **Regresión**: Para valores numéricos continuos (ej. predecir el precio de una casa). Se evalúa usando métricas de error como MAE, MSE, RMSE y $R^2$.
    * 🗂️ **Clasificación**: Para categorías (Binaria o Multiclase). Utiliza funciones probabilísticas (como Softmax u OVR) para decidir la clase ganadora.
* 🕵️ **Aprendizaje No Supervisado (Clustering)**: Encuentra patrones en datos sin etiquetas (ej. algoritmo K-means iterando con centroides).
* 🕸️ **Deep Learning**: Usa Redes Neuronales Artificiales de múltiples capas. El aprendizaje ocurre mediante un proceso iterativo: *Forward Pass*, cálculo de la Función de pérdida, Optimización (Descenso del gradiente) y Retropropagación (Backpropagation) para ajustar los pesos.

---

## ☁️ El Ecosistema Microsoft Azure y Foundry
Las aplicaciones de IA se componen de cuatro capas: Datos, Modelo (entrenamiento), Cómputo e Integración (APIs). 

* 🏭 **Microsoft Foundry**: Plataforma unificada (PaaS) para construir y desplegar aplicaciones empresariales. Ofrece un catálogo con miles de modelos (GPT-4, Llama) y gobernanza de IA responsable.
* 🏗️ **Infraestructura de Azure**: Se organiza jerárquicamente en: Inquilino (Tenant), Suscripción, Grupo de Recursos y el Recurso individual.
* 🔌 **Conexión**: Los servicios se consumen mediante *Endpoints* (URLs) y se autentican con *Keys* secretas enviadas en el *Header*.

### 🔄 Flujo de Trabajo en Azure Machine Learning
1. 🎯 **Definición del problema**: Determinar la tarea de ML y las métricas de éxito.
2. 🚰 **ETL/ELT**: Ingesta y preparación de datos desde diversas fuentes hacia un almacenamiento centralizado (ej. Azure Blob Storage).
3. 🏋️ **Entrenamiento**: Uso de recursos de cómputo (CPU/GPU) o AutoML para iterar algoritmos de forma automática.
4. 🚀 **Implementación (Endpoints)**:
    * ⚡ *Tiempo Real*: Resultado inmediato, infraestructura siempre activa (ej. AKS).
    * 📦 *Por Lotes (Batch)*: Para grandes volúmenes en momentos específicos, se apaga al terminar para ahorrar costos.

---

## 💬 Profundizando en LLMs y Análisis de Texto (NLP)
Los modelos de lenguaje no hacen "magia", predicen el siguiente token basándose en estadística avanzada.

* 🧩 **Tokenización y Embeddings**: El texto se fragmenta en tokens y se convierte en vectores (listas de números). Las palabras con significado similar se sitúan cerca en un espacio multidimensional.
* 🤖 **Arquitectura Transformer**: Tiene un *Codificador* (usa mecanismos de "Atención" para analizar el contexto) y un *Decodificador* (predice el siguiente token).
* 🧠 **RAG y Memoria**: Técnicas como RAG (Generación Aumentada por Recuperación) inyectan datos reales de fuentes externas (ej. PDFs) al prompt para evitar alucinaciones del modelo.

### 📐 Análisis Vectorial Semántico
Gracias a los Embeddings, podemos realizar operaciones lógicas con conceptos.
* 📐 **Similitud de Coseno**: Mide la cercanía espacial entre palabras.
* ⚖️ **Razonamiento Analógico**: Permite resolver analogías con vectores, por ejemplo:
    $V_{cachorro} - V_{joven} + V_{viejo} = V_{perro}$
    $V_{madrid} - V_{españa} + V_{francia} \approx V_{paris}$

### 🧹 Limpieza y Procesamiento de NLP
Antes de procesar, el texto crudo pasa por Normalización, eliminación de *Stop Words*, Lematización/Stemming y análisis estadístico como **TF-IDF** (para resaltar palabras únicas y relevantes).

---

## 🧩 Servicios Cognitivos de Azure

### 📝 1. Servicio de Lenguaje y Texto
* 🕵️ **Reconocimiento de Entidades (NER)** y Detección de Información Sensible (PII).
* 🎭 **Análisis de Sentimiento**: Evalúa el tono (Positivo, Neutral, Negativo) extrayendo frases clave.
* 🌐 **Azure Translator**: Utiliza Traducción Automática Neuronal (NMT) para traducir texto o documentos enteros manteniendo el formato original.

### 🎙️ 2. Tecnologías de Voz (Azure Speech)
* 👂 **Speech-to-Text (Reconocimiento)**: Convierte audio a texto extrayendo coeficientes MFCC, procesándolos acústicamente y decodificándolos en tiempo real o por lotes (Batch).
* 🗣️ **Text-to-Speech (Síntesis)**: Genera audio fluido pasando por Normalización, Análisis Lingüístico (G2P), Generación de Prosodia (ritmo y entonación) y uso de Vocoders neuronales (ej. WaveNet).
* 🌍 **Traducción de Voz**: Actúa como intérprete universal en tiempo real.

### 👁️ 3. Computer Vision y Extracción de Documentos
* 🖼️ **Visión por Computadora**: Analiza matrices de datos (RGB/Grises) mediante filtros de Convolución (CNN) para detectar características. Las arquitecturas modernas incluyen Visión Transformers (ViT) y modelos de Difusión para generar imágenes.
* 👤 **Azure AI Face**: Verifica y reconoce rostros, detecta el uso de cubrebocas y evalúa la "viveza" (Liveness) para evitar fraudes.
* 📜 **Flujo OCR**: Adquisición $\rightarrow$ Procesamiento (limpieza/contraste) $\rightarrow$ Detección de Regiones $\rightarrow$ Reconocimiento de Caracteres $\rightarrow$ Posprocesamiento.
* 📑 **Azure Document Intelligence**: Modelos precompilados que extraen pares clave-valor y estructuras tabulares complejas de facturas, recibos o documentos legales.

### 🔍 4. Minería de Conocimiento (Azure AI Search)
Extrae información de grandes volúmenes de archivos no estructurados.
1. 🗂️ **Indexador**: Recorre los datos.
2. ⚙️ **Conjunto de Aptitudes (Skillset)**: Aplica una cadena de tareas de IA (ej. OCR $\rightarrow$ NLP $\rightarrow$ Visión).
3. 🗄️ **Índice / Almacén**: Genera un motor de búsqueda interno y guarda los datos estructurados para análisis en herramientas como Power BI.
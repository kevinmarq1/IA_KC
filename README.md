# 🧠 Asistente Barman Virtual (Proyecto RAG en Local)

Este proyecto es una **implementación didáctica** de un sistema RAG (*Retrieval-Augmented Generation*) que responde preguntas sobre recetas de cócteles usando como única fuente un PDF local. La arquitectura combina un buscador semántico con un modelo de lenguaje, sin depender de APIs externas, ideal para pruebas educativas, experimentación o demostraciones.

---

## 📌 ¿Qué es un RAG?

RAG combina dos mundos:
- **Retriever**: recupera información relevante desde una base de documentos.
- **Generator**: responde preguntas en lenguaje natural usando el contexto obtenido.

En este caso, el modelo aprende a responder consultas como:
> _¿Qué cóctel puedo hacer con ron y jugo de naranja?_

... usando exclusivamente un documento PDF con recetas de barman.

---

## 🔧 Tecnologías utilizadas

- `Python 3.10+`
- `LangChain` – Marco modular para sistemas LLM.
- `FAISS` – Motor de búsqueda vectorial local.
- `Transformers` – Modelo de lenguaje (Flan-T5).
- `PyMuPDF (fitz)` – Extracción de texto del PDF.
- `HuggingFace Embeddings` – Vectorización semántica.
- `gdown` – Descarga directa desde Google Drive.

---

## 📦 Requisitos e instalación

### 1. Clona el repositorio

```bash
git clone https://github.com/tu-usuario/barman-rag-local.git
cd barman-rag-local
```

pip install -r requirements.txt
---
🚀 Cómo usar
🧪 Modo notebook (interactivo)
Abre el notebook Practica_IA_KC_KevinML.ipynb (por ejemplo en Colab o Jupyter).

Ejecuta las celdas paso a paso.

Realiza preguntas en lenguaje natural como:

¿Qué coctel puedo preparar con jugo de piña y ron?
El sistema extrae texto del PDF, lo vectoriza con FAISS, busca el contexto más relevante y genera una respuesta usando Flan-T5, todo en local.
---
barman-rag-local/
│
├── data/                     ← Carpeta para el PDF y texto procesado
├── modules/                  ← Código modular dividido en:
│   ├── loader.py             ← Carga y divide el PDF en chunks
│   ├── embedder.py           ← Carga modelo de embeddings
│   ├── retriever.py          ← Crea y/o guarda el índice FAISS
│   ├── generator.py          ← Llama al modelo Flan-T5 con contexto
│   └── main.py               ← Script de prueba funcional automática
│
├── Practica_IA_KC_KevinML.ipynb  ← Notebook principal paso a paso
├── README.md
└── requirements.txt
---
📝 Consideraciones
Este proyecto no es perfecto: el modelo puede dar respuestas incongruentes o inexactas. No está entrenado con recetas, solo genera texto a partir del contexto.

Sirve como base funcional y didáctica para explorar arquitectura RAG.

Todo se ejecuta en local: sin claves API, sin costes externos, ideal para aprender sin depender de OpenAI, Anthropic o Hugging Face Spaces.

📚 Créditos
Desarrollado como parte del módulo de Inteligencia Artificial del bootcamp KeepCoding Big Data & Machine Learning.
Inspirado en aplicaciones reales de RAG para asistentes conversacionales.

💡 Ideas de mejora
Reemplazar el modelo por uno más pequeño o especializado (ej: bart, t5-small).

Usar múltiples documentos PDF o cargar datos desde una base de datos.

Crear una interfaz web con Gradio o Streamlit.

Añadir un sistema de feedback para validar respuestas.

📜 Licencia
Este proyecto es de libre uso para fines educativos.

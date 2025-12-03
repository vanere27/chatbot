# Chatbot: Sistemas Inteligentes (Flask + GPT4All local + RAG local)

## Requisitos
- Windows 10/11
- Python 3.10/3.11
- Espacio en disco para modelos (varía por modelo; usualmente 200MB–2GB+)

## Instalación (PowerShell)
1. Clona o copia el proyecto.
2. Abre PowerShell en la carpeta del proyecto.
3. Crear virtualenv y activarlo:
   python -m venv .venv
   .\.venv\Scripts\Activate.ps1
   (si PowerShell bloquea scripts: Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process)
4. Instalar dependencias:
   python -m pip install --upgrade pip
   pip install -r requirements.txt
5. Descargar un modelo GPT4All y ponerlo en ./models/ (ver instrucciones abajo).
6. Copiar .env.example a .env y ajustar `GPT4ALL_MODEL_PATH` y `USE_GPT4ALL`.
7. Indexar corpus:
   python scripts\index_corpus.py --data .\data\corpus --out .\vectorstore\vectorstore.pkl --model all-MiniLM-L6-v2
   (si falla por RAM, usa paraphrase-MiniLM-L6-v2)
8. Ejecutar:
   python app.py
9. Abrir http://localhost:5000

## Notas
- Si `USE_GPT4ALL=false` o GPT4All falla se usa el modo "solo-corpus": el bot devuelve fragmentos del corpus.
- Modelos GPT4All se descargan desde https://gpt4all.io/models/ o GitHub releases de gpt4all (elige un modelo GGML/quantizado).

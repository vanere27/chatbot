# chatbot
# Chatbot: Sistemas Inteligentes (Flask + RAG local)

## Requisitos
- Python 3.10/3.11
- Windows 10/11

## Instalación (Windows, PowerShell)
1. Clonar o copiar el proyecto.
2. Abrir PowerShell en la carpeta del proyecto.
3. Crear virtualenv y activar:
   python -m venv .venv
   .\.venv\Scripts\Activate.ps1
4. Instalar dependencias:
   pip install -r requirements.txt
5. Copiar .env.example a .env y ajustar si usarás OpenAI.
6. Indexar corpus:
   python scripts\index_corpus.py --data .\data\corpus --persist .\chroma_db --model all-MiniLM-L6-v2
7. Ejecutar servidor:
   python app.py
8. Abrir http://localhost:5000

## Tests
Moverse a la raíz del proyecto (con el venv activo):
pytest -q

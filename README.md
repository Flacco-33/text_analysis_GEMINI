# Proyecto de análisis de texto

Este proyecto analiza las emociones y sentimientos de textos usando la API de Gemini en un Jupyter Notebook. 

## Instalación

1. **Crear un entorno virtual:**
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

2. **Instalar las dependencias:**
   ```bash
   pip install -r requirements.txt
   ```

## Estructura del Proyecto

La estructura del proyecto es la siguiente:

- `.gitignore`: Archivos y directorios ignorados por Git.
- `.idx/`: Configuraciones específicas del entorno de desarrollo.
- `.vscode/`: Configuraciones específicas de Visual Studio Code.
- `main.ipynb`: Jupyter Notebook principal que contiene el código para el análisis de texto.
- `README.md`: Este archivo, que proporciona información sobre el proyecto.
- `requirements.txt`: Lista de dependencias necesarias para ejecutar el proyecto.

## Uso
1. **Obtener una clave API de Gemini:**
   Para comenzar, [obtén una clave API](https://g.co/ai/idxGetGeminiKey) y reemplaza la palabra `TODO` a continuación con tu clave API:

2. **Configurar el modelo:**
   En el archivo `main.ipynb`, configura el modelo de generación de contenido:
   ```python
      import google.generativeai as genai
      genai.configure(api_key=API_KEY)

      generation_config = {
          "temperature": 0,
          "top_p": 0.95,
          "top_k": 64,
          "max_output_tokens": 8192,
          "response_mime_type": "text/plain",
      }

      model = genai.GenerativeModel(
          model_name='gemini-1.5-flash',
          generation_config=generation_config,
      )  
   ```
3. **Ejecutar el análisis:**
   Proporciona un texto de entrada `prompt` y ejecuta las celdas del notebook para obtener el análisis de emociones y sentimientos. El `prompt` debe incluir un identificador para referenciar a un docente específico. El formato del prompt debe ser el texto seguido de una coma y luego el identificador del docente. Por ejemplo, `"prompt_ejemplo,20ASC43"`, donde "prompt_ejemplo" es el texto de entrada y "20ASC43" es el identificador del docente.
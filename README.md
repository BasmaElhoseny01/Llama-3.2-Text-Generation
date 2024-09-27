
# Llama-3.2-Text-Generation

![image](https://github.com/user-attachments/assets/7de6ee3c-fddb-4231-a51d-666940ed1f8f)


This notebook demonstrates the use of the **Llama 3.2 model** by Meta for text generation using the Hugging Face `transformers` library. It runs on a Google Colab environment with a GPU (T4).

> **Important Note**: To gain access to the Llama 3.2 model, you need to request access from Hugging Face. Visit the [Llama 3.2 model page](https://huggingface.co/meta-llama/Llama-3.2-1B) and follow the instructions to request access. Ensure you have a valid API key to authenticate with Hugging Face.  
> **Quick Response**: The approval process is typically fast. For example, I received access within 15 minutes after submitting the request.

## Contents of the Notebook

1. **Installation of Required Libraries**:
   - Installs the `transformers` library needed for model usage.
   ```bash
   !pip install transformers
   ```

2. **Authentication with Hugging Face**:
   - Logs into Hugging Face Hub using an API key to access the Llama 3.2 model.
   ```python
   from huggingface_hub import login
   api_key = "your_hugging_face_api_key"
   login(api_key)
   ```

3. **Model Loading**:
   - Loads the Llama 3.2 model from Hugging Face and sets up a pipeline for text generation.
   ```python
   from transformers import pipeline
   model_id = "meta-llama/Llama-3.2-1B"
   text_generation_pipe = pipeline("text-generation", model=model_id)
   ```

4. **Text Generation**:
   - Defines a function `generate_text()` that takes an input text prompt and generates text using the Llama 3.2 model.
   ```python
   def generate_text(text, pipe):
       output = pipe(text)
       return output[0]['generated_text']
   ```

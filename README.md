
# Intelligent PDF Summarizer

Demo Link: https://youtu.be/AfM0BbgQSfQ

## Overview

The Intelligent PDF Summarizer is an Azure-based serverless application that automatically extracts text from uploaded PDF files, summarizes the content using Azure OpenAI (GPT-4), and stores the result as a new file in a separate output container.

## Architecture

1. A user uploads a PDF into the **`input`** container.
2. A **Blob Trigger Function** is activated.
3. The orchestrator function runs three activities:
   - `analyze_pdf`: Extracts text using Form Recognizer.
   - `summarize_text`: Summarizes the text using GPT-4.
   - `write_doc`: Saves and uploads the summarized content to the **`output`** container.

---

## Setup

1. **Clone the repository**  
   ```bash
   git clone https://github.com/your-username/intelligent-pdf-summarizer.git
   cd intelligent-pdf-summarizer

2. **Set up a virtual environment**
   ```bash
   python -m venv .venv
   .venv\Scripts\activate  # on Windows
   pip install -r requirements.txt

3. **Update local.settings.json**

4. **Start the Azure Functions host**
   ```bash
   func start --verbose

🩺 Medical Prescription Reader

A robust Python web application designed to digitize handwritten clinical documents. Powered by the **DeepSeek-OCR-2** model and wrapped in a user-friendly **Gradio** interface, this tool tackles one of the hardest OCR challenges: doctor's handwriting. 

Unlike standard Large Language Models that try to summarize or guess medical text, this application uses a highly-restrictive prompting architecture to force **literal, line-by-line transcription**, preventing hallucinations and ensuring accurate extraction of medicines, dosages, and instructions.

✨ Features

* **Strict Literal Extraction:** Bypasses LLM conversational habits to extract exactly what is written, ignoring the urge to summarize or hallucinate patient details.
* **Visual Grounding (Bounding Boxes):** Automatically draws bounding boxes around extracted text on the original image, allowing users to easily verify the source of the transcription.
* **Multi-Tabbed UI:** Clean Gradio 6.0 interface separating the Extracted Text, Visual Bounding Boxes, and Raw Model Output.
* **PDF & Image Support:** Built-in handling for standard image formats and complex image transposing.

🛠️ Tech Stack

* **Model:** [`deepseek-ai/DeepSeek-OCR-2`](https://huggingface.co/deepseek-ai/DeepSeek-OCR-2) (via Hugging Face Transformers)
* **Interface:** [Gradio 6.0](https://gradio.app/)
* **Backend:** PyTorch, Pillow (PIL), Regex

🚀 Installation

1. Prerequisites
You will need an environment with a GPU (CUDA) for the DeepSeek-OCR-2 model to run in a reasonable amount of time. 

You also need the `dejavu` system fonts installed for the bounding box rendering to work correctly.
* **Ubuntu/Debian:** `sudo apt-get install -y fonts-dejavu-core`

2. Clone the Repository
```bash
git clone [https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git](https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git)
cd YOUR_REPOSITORY_NAME

```

3. Install Dependencies

It is recommended to use a virtual environment. Install the required Python packages:

```bash
pip install torch torchvision transformers==4.46.3 tokenizers==0.20.3 accelerate einops addict easydict PyMuPDF hf_transfer spaces gradio numpy pillow

```

💻 Usage

Run the Gradio application by executing the Python script:

```bash
python app.py

```

1. Open the local URL provided in your terminal (usually `http://127.0.0.1:7860`).
2. Upload an image of a handwritten prescription.
3. Click **Analyze Prescription**.
4. Navigate through the tabs to view the cleaned text, the generated bounding boxes, and the raw internal model output.

⚠️ Privacy & Security Warning

**Do not upload sensitive Personal Health Information (PHI) or Personally Identifiable Information (PII) to public instances of this application.** If you are deploying this in a production medical environment, ensure you are running the model locally on secure, HIPAA-compliant servers, and that patient names, addresses, and ID numbers are redacted prior to processing.

🤝 Contributing

Contributions, issues, and feature requests are welcome!

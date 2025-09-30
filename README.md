# SKYLOGIC
This repository contains the implementation for Project SkyLogic , which integrates a frozen vision encoder with a frozen GPT-OSS LLM. By training only a lightweight projection layer, the system efficiently aligns visual features from ISRO satellite data with text embeddings to produce conversational reports.

# :star2: About the Project

<b>The Problem:</b>
<p>Analyzing Earth Observation (EO) satellite data from agencies like ISRO is crucial for monitoring environmental changes, urban planning, and resource management. However, this data is often complex and requires specialized expertise to interpret, creating a significant accessibility gap for policymakers, researchers, and the general public. While large language models (LLMs) excel at generating human-readable insights, they lack native vision capabilities to process this geospatial imagery directly. This project addresses the challenge of enhancing a text-only, open-source Generative Pre-trained Transformer (GPT-OSS) with multimodal vision capabilities.</p>

<b>Our Solution:</b>
<p>
The core of our solution is a lightweight projection layer that aligns outputs from a vision encoder with the text embedding space of a frozen GPT-OSS model.This approach significantly reduces training complexity and computational costs while preserving the powerful text reasoning capabilities of the large language model (LLM).</p>


## ✨ Key Features

* **Efficient Training**: Keeps the vision encoder and LLM frozen, only training the lightweight projection layer, which saves 20-65x in compute costs.
* **ISRO Data Focused**: Tailored to process and interpret ISRO's Level-1 and Level-2 satellite products.
* **Natural Language Insights**: Transforms complex satellite imagery into human-readable explanations for tasks like land cover classification, change detection, and environmental monitoring.
* **Accessible AI**: Makes complex geospatial data analysis accessible to non-experts through conversational Q&A and automated reports.

## 🛠️ Technical Approach

The model uses a two-stage training process:
1.  **Alignment**: First, align general image-caption pairs to teach the projection layer the relationship between visual and textual concepts.
2.  **Fine-Tuning**: Then, fine-tune the model on specific ISRO EO datasets to specialize its capabilities for land cover analysis, change detection, and environmental monitoring.

## 🚀 Getting Started

### Prerequisites
- Python 3.8+
- PyTorch
- GDAL/Rasterio
- A GPU with at least 16 GB of VRAM is recommended for efficient training.

### Installation
1.  Clone the repository:
    ```bash
    git clone [https://github.com/ay-crypt/SKYLOGIC.git](https://github.com/ay-crypt/SKYLOGIC.git)
    cd SKYLOGIC
    ```
2.  Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```

### Usage
Run the main pipeline script:
```bash
python src/main.py

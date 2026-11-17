# LATENT-SIGHT
## Bounding-Box Guided Latent Visual Reasoning for Vision-Language Models

LATENT-SIGHT explores region-guided visual reasoning in Vision-Language Models (VLMs). It combines interactive Region of Interest (ROI) selection, visual token mapping and a latent visual reasoning pipeline to investigate how selected image regions can support targeted visual understanding.

### Architecture

- Baseline model: SmolVLM-256M-Instruct
- Visual processor: Qwen2.5-VL processor
- Backend: FastAPI
- Frontend: HTML, CSS and JavaScript
- ROI selection: Interactive bounding-box selection
- Visual token mapping: Image-region-to-token mapping
- LVR components: Dataset processing, visual feature integration and custom forward-pass implementation
- Evaluation dataset: 20 annotated images

### Implemented Features

- Image upload and visualization.
- Interactive bounding-box selection.
- ROI-to-visual-token mapping.
- Visual token-grid highlighting.
- Baseline image question answering.
- Dataset evaluation and error analysis.
- Evaluation result visualization.

### Experimental Evaluation

The project includes baseline and dataset evaluation experiments.

Evaluation components include:

- Baseline response evaluation.
- Text-overlap precision, recall and F1 metrics.
- Category-wise performance analysis.
- Manual response review.
- Error analysis.
- Inference-time visualization.

Detailed experimental outputs are available in the `outputs/` directory.

The current evaluation is preliminary and does not establish an accuracy improvement from latent visual reasoning.

### Setup

1. Install a compatible Python environment.
2. Clone the repository.
3. Create and activate a virtual environment.
4. Install dependencies from `requirements.txt`.
5. Install website-specific dependencies.
6. Start the FastAPI application.

```bash
git clone https://github.com/cvsudharshan0401-lgtm/LATENT-SIGHT.git

cd LATENT-SIGHT

python -m venv .venv

source .venv/bin/activate

pip install -r requirements.txt

pip install -r website/requirements.txt
```

### Run the Website

```bash
cd website

uvicorn app:app --reload
```

Open the application:

```text
http://127.0.0.1:8000
```

API documentation:

```text
http://127.0.0.1:8000/docs
```

### Main Components

**Website**
- `website/app.py`
- `website/model_service.py`
- `website/static/script.js`

**ROI and Visual Mapping**
- `mac_demo/annotate_roi.py`
- `mac_demo/feature_comparison.py`
- `mac_demo/verify_roi_alignment.py`
- `mac_demo/validate_lvr_mapping.py`

**Dataset and Model Integration**
- `src/dataset/lvr_sft_dataset.py`
- `src/dataset/lvr_sft_dataset_packed.py`
- `src/model/qwen_lvr_model.py`
- `src/train/train_lvr.py`

**Evaluation**
- `evaluation/baseline_evaluation.py`
- `evaluation/dataset_evaluation.py`
- `evaluation/advanced_metrics.py`
- `evaluation/final_error_analysis.py`
- `evaluation/visualize_results.py`

### Project Structure

```text
LATENT-SIGHT/
├── website/
│   ├── app.py
│   ├── model_service.py
│   ├── static/
│   └── templates/
│
├── src/
│   ├── dataset/
│   ├── model/
│   ├── train/
│   └── trainer/
│
├── mac_demo/
│   ├── data/
│   ├── images/
│   ├── outputs/
│   └── testing scripts
│
├── evaluation/
│   ├── dataset/
│   └── evaluation scripts
│
├── outputs/
│   ├── baseline_evaluation/
│   └── dataset_evaluation/
│
├── research/
├── scripts/
├── requirements.txt
├── environment.yaml
└── README.md
```

### Model Artifacts

The repository contains ROI feature comparison outputs, token-mapping experiments and evaluation results.

Full Qwen2.5-VL-7B model weights and a trained custom LVR checkpoint are not included. Full-scale model training remains future work.

### Hardware

The development and lightweight validation environment includes:

- Apple MacBook Air M3
- 8 GB unified memory
- macOS
- Python virtual environment

The Mac environment is used for website development, processor-level token mapping and lightweight validation. Full-scale Qwen2.5-VL-7B training requires suitable GPU hardware.

### Dataset

A 20-image annotated evaluation dataset is included in `evaluation/dataset/`.

Additional ROI annotations and experimental data are available in `mac_demo/data/`.

### Future Work

- Complete end-to-end LVR model integration.
- Validate the custom model forward pass.
- Perform full-scale model training on GPU hardware.
- Expand evaluation datasets and benchmarks.
- Compare ROI-guided reasoning against baseline approaches.
- Investigate adaptive visual reasoning budgets.


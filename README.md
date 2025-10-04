
# SDXL‑Turbo Practical Demo (Text‑to‑Image in 1 Step)

This package contains a ready‑to‑run Jupyter notebook demonstrating **near real‑time text‑to‑image generation** with **SDXL‑Turbo** using the 🤗 `diffusers` library.

## Contents
- `GenAI_Demo_SDXL_Turbo.ipynb` — main notebook (single and batch image generation)
- `requirements.txt` — Python package requirements
- `README.md` — setup, run instructions, and troubleshooting tips

## Prerequisites
- Python 3.9+ (3.10+ recommended)
- (Optional) NVIDIA GPU + CUDA for best performance. CPU works at lower resolutions.
- Disk space: ~2–6 GB for models/caches (varies).

## Quick Start (Local)
1. **Create and activate a virtual environment (recommended)**
   ```bash
   python -m venv .venv
   # Windows
   .venv\Scripts\activate
   # macOS/Linux
   source .venv/bin/activate
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Launch Jupyter and open the notebook**
   ```bash
   python -m pip install jupyter
   jupyter notebook GenAI_Demo_SDXL_Turbo.ipynb
   ```

4. **Run the cells**. First run will download the `stabilityai/sdxl-turbo` weights.

## Optional: Hugging Face Authentication
If you encounter rate limits or want access to gated/private models:
- Get a token at https://huggingface.co/settings/tokens
- In the notebook, set `use_hf = True` and paste your token when prompted.

## Usage Notes
- **Image size**: Start with `576–640px`. Increase if you have more VRAM.
- **Steps**: SDXL‑Turbo works in **1 step**. For slightly higher quality, try **2–4** steps.
- **Guidance scale**: 0.0–1.5 usually works best.
- **Batch generation**: The notebook includes a cell that renders several prompts at once and saves PNGs to the working directory.

## Example Prompts
- *"a photorealistic close‑up of a golden retriever wearing sunglasses, soft studio lighting"*  
- *"a watercolor illustration of a mountain village at sunrise"*  
- *"a cinematic cyberpunk alley, wet asphalt, neon reflections, 85mm bokeh"*  
- *"a product hero shot of a wireless earbud on a marble slab, soft studio lighting, 50mm lens"*

## Troubleshooting
- **CUDA out of memory**: Reduce `height/width`, batch size, or use CPU.
- **Slow on CPU**: Decrease image size; expect longer inference time.
- **Model download errors**: Ensure internet connectivity or authenticate with Hugging Face.
- **Import errors**: Reinstall packages: `pip install --upgrade diffusers transformers accelerate torch safetensors`.

## Licensing & Responsible Use
- Review the model card and license for `stabilityai/sdxl-turbo` before commercial use.
- Follow local policies and ethics guidelines for generated content.

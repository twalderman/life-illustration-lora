# Life Illustration LoRA for Z-Image-Turbo

A custom-trained LoRA that generates **Laerdal Life Illustration** style images—flat vector art with faceless characters used in medical and healthcare training materials.

![Life Illustration Style](https://raw.githubusercontent.com/twalderman/life-illustration-lora/main/samples/example.png)

## Quick Start

```bash
# Using ZImageCLI (Mac)
ZImageCLI \
  -p "life_illustration, healthcare worker standing in clinic" \
  --lora life_design_zit_000002250.safetensors \
  --lora-scale 1.0 \
  -s 9 -o output.png
```

**Trigger Word**: `life_illustration`

---

## Requirements

### Base Model
- **[Z-Image-Turbo](https://huggingface.co/Tongyi-MAI/Z-Image-Turbo)** (Tongyi-MAI)
  - Distilled FLUX model optimized for 8-9 step inference
  - ~12GB download

### Image Generation Client (Mac)

| App | Z-Image Support | LoRA Support | Notes |
|-----|-----------------|--------------|-------|
| **AIbstraction Studio** | Yes | Yes | **Purpose-built** for Life Design assets (coming soon) |
| **[Draw Things](https://drawthings.ai)** | Yes | Yes | Native Mac app, easy to use |
| **[MindCraft Studio](https://themindstudio.cc/mindcraft)** | Yes | Yes | Based on mflux, Apple Silicon optimized |
| **[ComfyUI](https://github.com/comfyanonymous/ComfyUI)** | Yes | Yes | Most flexible, requires setup |
| **[ZImageCLI](https://github.com/twalderman/ZImageCLI)** | Yes | Yes | Command-line tool |

### AIbstraction Studio (Recommended)

A custom Mac application purpose-built for creating Life Design assets with this LoRA. Features optimized workflows for healthcare illustration generation.

*Coming soon*

### Alternative: Draw Things

1. Download [Draw Things](https://apps.apple.com/app/draw-things-ai-generation/id6444050820) from the App Store
2. Go to **Settings > Models** and download Z-Image-Turbo
3. Load the LoRA file via **Settings > LoRAs**
4. Set LoRA scale to **0.8**
5. Use `life_illustration` as trigger word in your prompts

---

## Usage

### Prompt Format

Always include the trigger word at the start of your prompt:

```
life_illustration, [your description here]
```

### Example Prompts

```
life_illustration, healthcare worker standing in modern clinic
life_illustration, patient sitting on examination table
life_illustration, person at desk with laptop computer
life_illustration, medical professional explaining to patient
life_illustration, office workers in meeting room
```

### Recommended Settings

| Parameter | Value |
|-----------|-------|
| LoRA Scale | 0.8 (balanced) |
| Inference Steps | 9 (fast) or 16 (quality) |
| CFG Scale | 0 (Z-Image-Turbo default) |
| Resolution | 1024x1024 or 1024x1536 |

### LoRA Scale Guide

| Scale | Effect |
|-------|--------|
| 0.6 | Subtle style influence |
| 0.8 | Balanced |
| 1.0 | Design adherence (**recommended**) |
| 1.2 | Maximum style (may over-apply) |

---

## Training Details

| Parameter | Value |
|-----------|-------|
| Base Model | Z-Image-Turbo |
| Training Adapter | ostris/zimage_turbo_training_adapter_v2 |
| Training Steps | 3000 |
| LoRA Rank | 32 |
| Training Images | 369 |
| Trigger Word | `life_illustration` |

Trained using [AI-Toolkit](https://github.com/ostris/ai-toolkit) on RunPod (A40 GPU).

---

## Files

| File | Size | Description |
|------|------|-------------|
| `life_design_zit_000002250.safetensors` | 170 MB | **Recommended** - Step 2250 checkpoint |
| `life_illustration_zit_v2.safetensors` | 340 MB | Full precision variant |
| `samples/` | - | Example outputs |

---

## Limitations

- Optimized specifically for Z-Image-Turbo (may work with other FLUX models but untested)
- Best results with simple, clear prompts
- Medical/healthcare contexts work best (matches training data)
- Complex multi-character scenes may require prompt engineering

---

## License

This LoRA is released for **personal and educational use**.

The Life Illustration style is based on Laerdal Medical's Life Illustration style guide (private). This LoRA is an independent fan creation and is not officially affiliated with or endorsed by Laerdal Medical.

---

## Links

- **Figma Source**: [Life Illustration Library v2.2.0](https://www.figma.com/design/aKqGUBjSWByWm6LN2nBZdr/Ext.-Life-Illustration-Lib.-v2.2.0)
- **Base Model**: [Z-Image-Turbo on HuggingFace](https://huggingface.co/Tongyi-MAI/Z-Image-Turbo)
- **Training Framework**: [AI-Toolkit by ostris](https://github.com/ostris/ai-toolkit)
- **Laerdal Medical**: [laerdal.com](https://laerdal.com)

---

## Acknowledgments

- [Laerdal Medical](https://laerdal.com) for the Life Illustration style guide (private)
- [ostris](https://github.com/ostris) for AI-Toolkit and the Z-Image training adapter
- [Tongyi-MAI](https://huggingface.co/Tongyi-MAI) for Z-Image-Turbo

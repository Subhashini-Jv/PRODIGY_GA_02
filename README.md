
## Image Generation using Pre-trained Models

This project demonstrates **text-to-image generation** using a pre-trained generative AI model.
The implementation uses **Stable Diffusion**, which generates realistic images from natural language prompts.

---

## Objective

Use pre-trained generative models like **DALL·E Mini or Stable Diffusion** to generate images based on text prompts.

---

## Technologies Used

* Python
* PyTorch
* Hugging Face Diffusers
* Stable Diffusion
* Google Colab

---

## Project Structure

```
PRODIGY_GA_02
│
├── PRODIGY_GA_02.ipynb
├── generated_image.png
└── README.md
```

---

## Installation

Install required libraries:

```
pip install torch diffusers transformers accelerate safetensors pillow
```

---

## Code Example

```python
import torch
from diffusers import StableDiffusionPipeline

model_id = "runwayml/stable-diffusion-v1-5"

pipe = StableDiffusionPipeline.from_pretrained(
    model_id,
    torch_dtype=torch.float16
)

pipe = pipe.to("cuda")

prompt = "A futuristic city with flying cars and neon lights"

image = pipe(prompt).images[0]

image.save("generated_image.png")
```

---

## Output

Prompt used:

```
A futuristic city with flying cars and neon lights
```

The generated image is saved as **generated_image.png**.


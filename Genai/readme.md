## Voice Generation

from transformers import AutoProcessor, AutoModel

processor = AutoProcessor.from_pretrained("suno/bark-small")
model = AutoModel.from_pretrained("suno/bark-small")

inputs = processor(
    text=["Hello, my name is Suno. And, uh — and I like pizza. [laughs] But I also have other interests such as playing tic tac toe."],
    return_tensors="pt",
)

speech_values = model.generate(**inputs, do_sample=True)

from IPython.display import Audio

sampling_rate = model.generation_config.sample_rate
Audio(speech_values.cpu().numpy().squeeze(), rate=sampling_rate)



## text to image

```python
from transformers import pipeline
import torch
from diffusers import DiffusionPipeline

# Load the image generation pipeline using diffusers
generator = DiffusionPipeline.from_pretrained("CompVis/stable-diffusion-v1-4")
generator.to("cuda")

# Generate an image from the text prompt
prompt = "A beautiful landscape with mountains and a lake"
image = generator(prompt).images[0]
display(image)

```



## Pac Man Controll 
https://storage.googleapis.com/tfjs-examples/webcam-transfer-learning/dist/index.html


## Filter
https://holobooth.flutter.dev/















## Text To Image

<img width="1104" height="736" alt="image" src="https://github.com/user-attachments/assets/d73afeba-8e05-4bea-8b11-c68b1631bfda" />

## Text To Audio

<img width="1211" height="494" alt="image" src="https://github.com/user-attachments/assets/37437b61-640d-485d-9e83-9530e3398c74" />


## Suno Bark/Voice Generation



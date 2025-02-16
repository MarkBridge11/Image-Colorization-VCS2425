# Fine-Tuning Stable Diffusion with LoRA for Colorization task
_Repository containing project of A.A 24/25 of Vision and Cognitive System (VCS)._

**Members: Boraso Francesco, Brigo Marco, Pantaleo Fabio.**


The project involved fine-tuning a pre-trained Stable Diffusion model to accomplish Colorization task using LoRA technique.

In the Colorization task what we aim to do, is to give as input a gray image and colorize it, giving colors that resemble (ideally the same) its ground truth.

We crafted our RGB dataset based on Imagenette (full version), captioning images using BLIP model and removing black and white images. During training process we only trained the LoRA weights of the UNet of the Stable diffusion model, freezing its pre-trained VAE and text encoder. Captions of the images were passed to the UNet as text embeddings properly encoded.

**Dataset:**
- Imagenette (full version, for Training): https://github.com/fastai/imagenette
- ImageNet (Validation): https://huggingface.co/datasets/timm/imagenet-1k-wds
- MS-COCO (Testing): https://huggingface.co/datasets/nlphuji/mscoco_2014_5k_test_image_text_retrieval
  
**Models:**
- Stable-diffusion-2-1: https://huggingface.co/stabilityai/stable-diffusion-2-1
- blip-image-captioning-large: https://huggingface.co/Salesforce/blip-image-captioning-large

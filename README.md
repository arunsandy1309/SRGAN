# Stable Diffusion - TensorFlow Implementation
![output](https://user-images.githubusercontent.com/50144683/234247234-c2c263fb-a913-4ea6-a77a-0288e424786b.png)</br>
The above pictue is generated using the prompt "A epic and beautiful rococo werewolf drinking coffee, in a burning coffee shop. ultra-detailed. anime, pixiv, uhd 8k cryengine, octane render"

This repository contains the Pytorch implementation of the following paper:
>**High-Resolution Image Synthesis with Latent Diffusion Models**</br>
>Robin Rombach, Andreas Blattmann, Dominik Lorenz, Patrick Esser, Björn Ommer</br>
>https://arxiv.org/abs/2112.10752
>
>**Abstract:** _By decomposing the image formation process into a sequential application of denoising autoencoders, diffusion models (DMs) achieve state-of-the-art synthesis results on image data and beyond. Additionally, their formulation allows for a guiding mechanism to control the image generation process without retraining. However, since these models typically operate directly in pixel space, optimization of powerful DMs often consumes hundreds of GPU days and inference is expensive due to sequential evaluations. To enable DM training on limited computational resources while retaining their quality and flexibility, we apply them in the latent space of powerful pretrained autoencoders. In contrast to previous work, training diffusion models on such a representation allows for the first time to reach a near-optimal point between complexity reduction and detail preservation, greatly boosting visual fidelity. By introducing cross-attention layers into the model architecture, we turn diffusion models into powerful and flexible generators for general conditioning inputs such as text or bounding boxes and high-resolution synthesis becomes possible in a convolutional manner. Our latent diffusion models (LDMs) achieve new state-of-the-art scores for image inpainting and class-conditional image synthesis and highly competitive performance on various tasks, including text-to-image synthesis, unconditional image generation and super-resolution, while significantly reducing computational requirements compared to pixel-based DMs._

## Architecture
![image](https://user-images.githubusercontent.com/50144683/234249084-739a761c-60de-4ff5-8b6c-94a6b886266a.png)</br>
Latent Diffusion Models(LDMs) provide means to flexible and computationally tractable diffusion based image synthesis of various image modalities, which we empirically show in the following. Firstly, however, we analyze the gains of our models compared to pixel-based diffusion models in both training and inference. Interestingly, we find that LDMs trained in VQregularized latent spaces sometimes achieve better sample quality, even though the reconstruction capabilities of VQregularized first stage models slightly fall behind those of their continuous counterparts.

## Using `text2image.py` from the git repo

Assuming you have installed the required packages, 
you can generate images from a text prompt using:

```bash
python text2image.py --prompt="An astronaut riding a horse"
```

The generated image will be named `output.png` on the root of the repo.
If you want to use a different name, use the `--output` flag.

```bash
python text2image.py --prompt="An astronaut riding a horse" --output="my_image.png"
```

Check out the `text2image.py` file for more options, including image size, number of steps, etc.  

## Example outputs 

The following outputs have been generated using this implementation:

1) *A epic and beautiful rococo werewolf drinking coffee, in a burning coffee shop. ultra-detailed. anime, pixiv, uhd 8k cryengine, octane render*

![a](https://user-images.githubusercontent.com/1890549/190841598-3d0b9bd1-d679-4c8d-bd5e-b1e24397b5c8.png)


2) *Spider-Gwen Gwen-Stacy Skyscraper Pink White Pink-White Spiderman Photo-realistic 4K*

![a](https://user-images.githubusercontent.com/1890549/190841999-689c9c38-ece4-46a0-ad85-f459ec64c5b8.png)


3) *A vision of paradise, Unreal Engine*

![a](https://user-images.githubusercontent.com/1890549/190841886-239406ea-72cb-4570-8f4c-fcd074a7ad7f.png)

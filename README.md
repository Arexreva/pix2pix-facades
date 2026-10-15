# Pix2Pix: Image-to-Image Translation

## Overview
A PyTorch implementation of Pix2Pix for translating architectural facade label maps into realistic photographs.

## Architecture
- Generator: U-Net with skip connections.
- Discriminator: Conditional PatchGAN.
- Generator loss: adversarial loss + 100 * L1 reconstruction loss.

## Dataset
- Training images: 400
- Validation images: 100
- Test images: 106
- Image resolution: 256 x 256
- Task: Facade label map to facade photograph.

Dataset: https://efrosgans.eecs.berkeley.edu/pix2pix/datasets/facades.tar.gz

The dataset is not included in this repository.

## Results

| Model | MAE | PSNR (dB) |
|---|---:|---:|
| Pix2Pix (GAN + L1) | 0.1847 | 12.5658 |
| GAN-only ablation | 0.2446 | 10.2875 |

The full model performed better on these test metrics in this experiment.
Results depend on the implementation and training configuration.

See the results directory for the comparison figure and evaluation CSV.

## Installation
Install dependencies using:

pip install -r requirements.txt

## Running the Project
1. Clone this repository.
2. Install the dependencies.
3. Download and extract the Facades dataset.
4. Open the notebook in the notebooks directory.
5. Run the notebook cells in order.

A GPU is recommended for training.

## Ablation Study
The full model uses adversarial and L1 reconstruction losses.
The ablation removes the L1 reconstruction loss.
Both models were trained for 50 epochs.

## Limitations
This is a reduced-scale educational reproduction, not an exact reproduction of every experiment in the original paper.

## Reference
Isola et al., Image-to-Image Translation with Conditional Adversarial Networks, CVPR 2017.
Paper: https://arxiv.org/abs/1611.07004

## License
Add an appropriate license before redistributing this project.

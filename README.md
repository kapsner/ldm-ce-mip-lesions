# ldm-ce-mips-lesions

This repository contains supporting material of the publication [Lesion-conditioning of synthetic MRI-derived subtraction-MIPs of the breast using a latent diffusion model](https://www.nature.com/articles/s41598-024-56853-1).

Citation:

>Kapsner, L.A., Folle, L., Hadler, D. et al. Lesion-conditioning of synthetic MRI-derived subtraction-MIPs of the breast using a latent diffusion model. Sci Rep 14, 6391 (2024). https://doi.org/10.1038/s41598-024-56853-1

## Installation

At first, prepare your data accordingly and adjust the [config file](configs/latent-diffusion/dce_mip-vq-seg.yaml) as well as the [data loader](https://github.com/kapsner/latent-diffusion/blob/main/ldm/data/dce_mip.py).

To run the code, then execute the following commands:

```bash
git clone -b v0.1.0 https://github.com/kapsner/latent-diffusion
cd latent-diffusion

conda env create -f environment.yaml
conda activate ldm

export parameter_grid=./param_grid_230119.csv
export ldm_cfg=./configs/latent-diffusion/dce_mip-vq-seg.yaml
export results_folder=/home/user/development/trainings/diffusionmodels

python automate_learnings.py \
    -c $parameter_grid \
    -b $ldm_cfg \
    -l $results_folder
```

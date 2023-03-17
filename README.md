# ldm-ce-mips-lesions

To run the code, just execute the following commands:

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

Make sure to adjust the [config file](configs/latent-diffusion/dce_mip-vq-seg.yaml) accordingly, as well as the [data loader](https://github.com/kapsner/latent-diffusion/blob/main/ldm/data/dce_mip.py).

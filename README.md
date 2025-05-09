# Diffusion Fine-tuning as Constrained Optimization

This is a fork of the Diffusion Forcing repo on which we ran our constrained diffusion experiment for maze2d planning and point avoidance. See `original_README.md` for more details on the original Diffusion Forcing repo.

# Project Instructions

## Setup

Run `conda create python=3.10 -n diffusion-finetuning` to create environment.
Run `conda activate diffusion-finetuning` to activate this environment.

Install dependencies:

**IMPORTANT**: if you are not running this on macOS, please modify the `pyrealsense` package in `requirements.txt` to fit your device before installing requirements.

```
pip install -r requirements.txt
```

[Sign up](https://wandb.ai/site) a wandb account for cloud logging and checkpointing. In command line, run `wandb login` to login.

Then modify the wandb entity in `configurations/config.yaml` to your wandb account.

Please rename the folder `outputs_/` to `outputs/` to use the pre-trained diffusion forcing model.

## Run Fine-tuning on Diffusion Planner

We provide a bash script `maze_train.sh` to run our fine-tuning experiment.

First, please make the script executable.

```
chmod +x maze_train.sh
```

Then, run the script.

```
./maze_train.sh
```

## Modifications

### Constrained Diffusion Algorithm

```
algorithms/diffusion_forcing/df_planning.py
- Line 88 to 177

algorithms/diffusion_forcing/models/diffusion.py
- Line 274 to 347
```

### Hyperparamters

```
configurations/algorithm/df_planning.yaml
configurations/experiment/exp_planning.yaml
```

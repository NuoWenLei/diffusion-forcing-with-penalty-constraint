### Acknowledgement

This is a fork of the [Diffusion Forcing v1.5](https://github.com/buoyancy99/diffusion-forcing) repository. See `original_README.md` for more details on the original repository.

# Diffusion Fine-tuning as Constrained Optimization

This is the main repo of Diffusion Fine-tuning as Constrained Optimization, including code for our experiments on **Maze2D planning** and **MNIST**. Please see below for instructions to run both experiments.

# Instructions for Maze2D Planning

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
- Line 88 to 186

algorithms/diffusion_forcing/models/diffusion.py
- Line 274 to 347
```

### Hyperparamters

```
configurations/algorithm/df_planning.yaml
configurations/experiment/exp_planning.yaml
```

# Instructions for MNIST

### Run on Google Colab

Please open [this Google Colab notebook](https://colab.research.google.com/drive/1Z_-nJj-cXISLIB1u7WC6wD7sAcdq7JFs?usp=sharing), save a copy to your drive, and run it.

### View Locally

An `.ipynb` copy of the notebook is saved under the `mnist/` directory although the notebook **requires some of the packages installed in the Google Colab environment** to be ran.

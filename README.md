# Getting Started - Clone this Repo from your MI300 GPU Droplet

### Clone the Repo

##### Copy the below code and run it in a Jupyter notebook in the Digital Ocean GPU Droplet 
---
```Python
!pip install pygit2

import pygit2

# URL of the Git repository
repo_url = "https://github.com/andrewgschmidt/AMD_Hackathon.git"

# Path to clone into
local_path = "./AMD_Hackathon"

# Clone the repo
repo = pygit2.clone_repository(repo_url, local_path)

print("Repo cloned at:", repo.workdir)

!pip install torch==2.7.1 torchvision==0.22.1 torchaudio==2.7.1 --index-url https://download.pytorch.org/whl/rocm6.3

import torch
print(f'CUDA compatible device availability:',torch.cuda.is_available())
print(f'device name [0]:', torch.cuda.get_device_name(0))

!add-apt-repository ppa:ubuntuhandbook1/ffmpeg7 -y # install PPA which contains ffmpeg 7.x
!apt update && apt install ffmpeg -y

!git clone https://github.com/huggingface/lerobot.git
!cd lerobot && pip install -e .

!pip install wandb

print("Restart Kernel to reload after installing wandb")
```
---

##### Then copy and run this code after restarting the Kernel
---
```Python

## Update with Your WAMDB Key
import wandb
wandb.login(key="YOUR_WANDB_KEY!")

## Update with Your HuggingFace Key
from huggingface_hub import login
login(token="YOUR_HF_KEY")

```
---

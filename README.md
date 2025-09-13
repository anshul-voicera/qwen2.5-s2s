# Qwen2.5-Omni Audio Demo

In this folder:
- Inferencing with audio input and audio output
- Inferencing with video input and audio output
- Link to scripts for fine-tuning (not tested by Trellis)

## Setup

<img width="712" height="526" alt="image" src="https://github.com/user-attachments/assets/a6efcb28-43a0-4ad0-b906-8efa59fcb73d" />


### 1. Install required packages

> [TIP] If running locally, create a venv with `uv venv` and consider swapping the device to `mps` instead of `cuda` if using Mac.

Run:
```bash
cd speech-to-speech/qwen2.5-omni
pip install uv
uv pip install soundfile qwen-omni-utils[decord] hf_transfer --system

uv pip uninstall transformers torch torchvision torchaudio --system
uv pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121 --system
uv pip install git+https://github.com/huggingface/transformers@f742a644ca32e65758c3adb36225aef1731bd2a8 --system
uv pip install accelerate --system
uv pip install flash-attn --no-build-isolation --system

apt update
apt install ffmpeg -y


export HF_HUB_ENABLE_HF_TRANSFER=1
export HF_HOME="/workspace"
```

uv run run_audio.py --system

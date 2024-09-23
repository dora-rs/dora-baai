# dora-baai

1. Install dora-rs

> Check website for more install: https://dora-rs.ai/

```bash
curl --proto '=https' --tlsv1.2 -sSf https://raw.githubusercontent.com/dora-rs/dora/main/install.sh | bash
```

2. Clone dora-rs github repo

```bash
cd ..
git clone https://github.com:dora-rs/dora.git --branch qwenvl2

git clone https://github.com:hiyouga/LLaMA-Factory.git
```

3. Install Conda

4. Create a new env

```bash
conda create -y -n lebai python=3.10.12 && conda activate lebai
```

5. Install cargo

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

6. Install dora nodes

```bash

# For visualization
cargo install --force rerun-cli@0.15.1

cd robots/lebai
dora up
dora build graphs/keyboard_teleop.yml
```

7. Start the dataflow

```bash
dora start graphs/keyboard_teleop.yml
```


# On run


```bash
cd robots/lebai
conda activate lebai
dora up
dora start graphs/keyboard_teleop.yml
```

## For training the model

- Install llama-factory
```
pip install -e "../llama-factory[torch,metrics]"
```

- Modify `llama-factory/examples/train_lora/qwen2vl_lora_sft.yaml` so that the dataset is the one you want to use,

```yaml,diff
- dataset: mllm_demo,identity  # video: mllm_video_demo
+ dataset: dora_demo_107,identity`
```

- You can also choose the 2B model instead of the 7B model with

```yaml,diff
- model_name_or_path: Qwen/Qwen2-VL-7B-Instruct
+ model_name_or_path: Qwen/Qwen2-VL-2B-Instruct
```

- Then

```bash
llamafactory-cli train examples/train_lora/qwen2vl_lora_sft.yaml
```

## Qwenvl2

Make sure to install flash-attention 2 before installing qwenvl2

```bash
# Check version on: https://github.com/Dao-AILab/flash-attention/releases/tag/v2.6.3
# e.g.:
pip install https://github.com/Dao-AILab/flash-attention/releases/download/v2.6.3/flash_attn-2.6.3+cu123torch2.4cxx11abiFALSE-cp310-cp310-linux_x86_64.whl
```

> Make sure to use the abi False version. FYI, ABI means python compatible version.


Then

```bash
dora build qwenvl2.yml
```

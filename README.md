# dora-baai

## Install dora-rs

> Check website for more install: https://dora-rs.ai/

```bash
curl --proto '=https' --tlsv1.2 -sSf https://raw.githubusercontent.com/dora-rs/dora/main/install.sh | bash
```

## Clone dora-rs github repo

```bash
cd ..
git clone git@github.com:dora-rs/dora.git
git checkout qwenvl2
```

```bash
conda create -y -n lebai python=3.10.12 && conda activate lebai

cd robots/lebai
dora up
dora build keyboard_teleop.yml
dora start keyboard_teleop.yml
```

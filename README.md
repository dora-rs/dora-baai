# dora-baai

1. Install dora-rs

> Check website for more install: https://dora-rs.ai/

```bash
curl --proto '=https' --tlsv1.2 -sSf https://raw.githubusercontent.com/dora-rs/dora/main/install.sh | bash
```

2. Clone dora-rs github repo

```bash
cd ..
git clone git@github.com:dora-rs/dora.git --branch qwenvl2

git clone git@github.com:hiyouga/LLaMA-Factory.git
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
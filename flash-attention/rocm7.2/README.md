# Build Script for FlashAttention 2.8.3 on ROCm 7.2

This script is designed to build FlashAttention 2.8.3 on ROCm 7.2. It assumes that you have already set up your ROCm environment and have the necessary dependencies installed.

```bash
git clone git@github.com:Dao-AILab/flash-attention.git
git checkout v2.8.3

cd flash-attention

cp ../ML-helpers/flash-attention/rocm7.2/Pipfile Pipfile
cp ../ML-helpers/flash-attention/rocm7.2/Pipfile.lock Pipfile.lock

pipenv install -v

FLASH_ATTENTION_TRITON_AMD_ENABLE="TRUE" python -m build --wheel --no-isolation

# Your wheel file will be located in dist/ when the build is finished
```

For completeness, the resulting wheel file from my build is included here in this repository

This can be installed using
```bash

pip install "https://github.com/HenryJia/ML-helpers/raw/main/flash-attention/rocm7.2/flash_attn-2.8.3-py3-none-any.whl"
```
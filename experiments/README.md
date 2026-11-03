# Router-bias experimental scripts

These files are preserved byte-for-byte from `MoE_Optimization/MoE_auto_bias_experiments`. They contain the original exploratory implementation, including alternative bias-scaling rules and model-specific routines.

| Script | Hard-coded Hugging Face model |
| --- | --- |
| `legacy/WES_auto_bias_qwen1.5.py` | `Qwen/Qwen1.5-MoE-A2.7B` |
| `legacy/WES_auto_bias_qwen3.py` | `Qwen/Qwen3-30B-A3B-Instruct-2507` |
| `legacy/WES_auto_bias_phi.py` | `microsoft/Phi-3.5-MoE-instruct` |
| `legacy/WES_auto_bias_mixtral.py` | `mistralai/Mixtral-8x7B-Instruct-v0.1` |

## Status and protocol

The paper/poster reports Qwen experiments. Phi and Mixtral files are additional exploratory code, not evidence of reported paper results. The scripts have not been executed as part of this repository packaging.

These scripts are not a frozen reproduction of the paper protocol. In particular, the Qwen3 script loads calibration examples from MMLU `test` and reuses the mathematics subset for evaluation, whereas the manuscript specifies a non-test calibration set. It also hard-codes `Qwen3-30B-A3B-Instruct-2507` and activates one of several bias variants. Check and align the model revision, split separation, score definition, normalization/scaling, and selected variant before using the code to reproduce reported numbers.

## Environment and exploratory execution

Use a CUDA-capable machine with sufficient memory for the selected model. Hugging Face access is required to download models and `cais/mmlu`. Install a PyTorch build appropriate for the machine's CUDA configuration, then install the remaining dependencies:

```sh
python -m venv .venv
source .venv/bin/activate
# Install torch for your CUDA environment first.
python -m pip install -r experiments/requirements.txt
python experiments/legacy/WES_auto_bias_qwen3.py
```

`requirements.txt` lists direct dependencies without version pins; the original environment lockfile was not available. Model loading and MMLU download happen in the scripts, with dataset loading also occurring at import time. Avoid importing them as a library or test fixture. The scripts use hard-coded settings rather than a CLI. Review the selected file before launching a GPU job.

Some scripts append results to `WES_metrics.txt` in the working directory. No model checkpoints, calibrated biases, raw experiment outputs, or validated final-table reproduction commands are bundled.

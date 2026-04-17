# Paper 9: The Hardware Basin — Experiments & Code

**Why the Quantization Cliff Is About Level Allocation, Not Bit Count**

[![Status: Preprint](https://img.shields.io/badge/Status-Preprint-orange)](#)
[![License: MIT](https://img.shields.io/badge/Code-MIT-green)](https://opensource.org/licenses/MIT)
[![License: CC BY 4.0](https://img.shields.io/badge/Data-CC_BY_4.0-lightgrey)](https://creativecommons.org/licenses/by/4.0/)

---

## Published Paper

**[Windstorm-Institute/hardware-basin](https://github.com/Windstorm-Institute/hardware-basin)** — paper PDF, article HTML

**Website article:** [windstorminstitute.org/articles/hardware-basin.html](https://windstorminstitute.org/articles/hardware-basin.html)

**Zenodo:** DOI pending (preprint)

## Experiments

| Experiment | Directory | Key Result |
|---|---|---|
| Pure arithmetic cliff (P9-A) | `experiments/p9a_arithmetic_cliff/` | 5.0× cliff ratio at INT4→INT3 |
| Real Pythia-410M weights (P9-E4) | `experiments/p9_e4_real_weights/` | 4–5× cliff across all weight matrices |
| End-to-end BPT (Exp 3) | `experiments/exp3_e2e_bpt/` | Symmetric INT4 = BPT 16.9 (catastrophic) |
| Multi-model cliff (Exp 4) | `experiments/exp4_multi_model/` | Cliff in Pythia, GPT-2, AND Mamba |
| NF4 vs symmetric (P9-F1) | `experiments/p9_f1_nf4_vs_symmetric/` | NF4 INT4 = 3.90 BPT vs Sym INT4 = 16.87 |
| Level allocation analysis | `experiments/analysis_level_allocation/` | NF4: 0.973, Lloyd-Max: 0.990, Sym: 0.905 |
| Level allocation all models | `experiments/analysis_level_allocation_all/` | Universal across 4 architectures |
| GPT-2 outlier analysis | `experiments/analysis_outlier/` | Kurtosis 124.75 explains cliff resistance |
| Per-layer progression | `experiments/analysis_per_layer/` | Consistent 4.5× across all 24 layers |

## Hardware

- **GPU:** NVIDIA RTX 5090 (32 GB VRAM)
- **CPU:** Intel Core Ultra 9 285K (24 cores)
- **RAM:** 256 GB
- **Chipyard/Gemmini:** Built and ready (not yet used for cycle-accurate simulation)
- **OS:** Ubuntu 24.04, Python 3.12, PyTorch 2.11, bitsandbytes 0.49.2

## Reproduction

All CSVs in `experiments/*/results/` are raw outputs. Plots in `plots/`.
Training/analysis scripts are in: [Windstorm-Institute/throughput-basin-origin](https://github.com/Windstorm-Institute/throughput-basin-origin)

---

*Code: MIT License · Data: CC BY 4.0*

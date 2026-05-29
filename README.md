# Paper 9: The Hardware Basin — Experiments & Code

**Why the Quantization Cliff Is About Level Allocation, Not Bit Count**

[![DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.19672921-blue)](https://doi.org/10.5281/zenodo.19672921)
[![License: MIT](https://img.shields.io/badge/Code-MIT-green)](https://opensource.org/licenses/MIT)
[![Track: Throughput Basin](https://img.shields.io/badge/Track-1_·_Throughput_Basin-3b82f6)](https://windstorminstitute.org/#track1)
[![License: CC BY 4.0](https://img.shields.io/badge/Data-CC_BY_4.0-lightgrey)](https://creativecommons.org/licenses/by/4.0/)

---

## Published Paper

**[Windstorm-Institute/hardware-basin](https://github.com/Windstorm-Institute/hardware-basin)** — paper PDF, article HTML

**Website article:** [windstorminstitute.org/articles/hardware-basin.html](https://windstorminstitute.org/articles/hardware-basin.html)

**Zenodo (concept DOI, always-latest):** [10.5281/zenodo.19672921](https://doi.org/10.5281/zenodo.19672921) · **v2.2:** [10.5281/zenodo.19672922](https://doi.org/10.5281/zenodo.19672922)

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

- **GPU:** Current-generation Nvidia GPU (32 GB VRAM, CUDA)
- **CPU:** Intel Core Ultra 9 285K (24 cores)
- **RAM:** 256 GB
- **Chipyard/Gemmini:** Built and ready (not yet used for cycle-accurate simulation)
- **OS:** Ubuntu 24.04, Python 3.12, PyTorch 2.11, bitsandbytes 0.49.2

## Reproduction

All CSVs in `experiments/*/results/` are raw outputs. Plots in `plots/`.
Training/analysis scripts are in: [Windstorm-Institute/throughput-basin-origin](https://github.com/Windstorm-Institute/throughput-basin-origin) under `paper9/` and `weekend_experiments/p9_*/`, `weekend_experiments/decisive_round/exp6_lloydmax_int3/`, `weekend_experiments/grandslam/gs3_structural_bonus/`, `weekend_experiments/robust_round/r4_structural_bonus/`, and `weekend_experiments/final_round/p9_f1_nf4_int3/` and `p9_f2_level_allocation_all/`.

---

## Discuss this code

- **Bug, reproduction failure, or unexpected output?** → [Open an Issue](../../issues)
- **Q&A — version compatibility, hardware, generalization to other inputs?** → [Start a Discussion](../../discussions)
- **Discuss the paper itself** → [Comments on the website article](https://windstorminstitute.org/articles/hardware-basin.html#comments) or [Issues on the Institute repo](https://github.com/Windstorm-Institute/hardware-basin/issues)

---

---

## The Windstorm Institute — Two Research Tracks

### Track 1 — The Throughput Basin · 9 papers (Papers 1–9 globally; 1st through 9th in this track; arc complete)

| # | Paper | DOI |
|---|-------|-----|
| 1 | [The Fons Constraint](https://github.com/Windstorm-Institute/fons-constraint) | [10.5281/zenodo.19274048](https://doi.org/10.5281/zenodo.19274048) |
| 2 | [The Receiver-Limited Floor](https://github.com/Windstorm-Institute/receiver-limited-floor) | [10.5281/zenodo.19322973](https://doi.org/10.5281/zenodo.19322973) |
| 3 | [The Throughput Basin](https://github.com/Windstorm-Institute/throughput-basin) | [10.5281/zenodo.19323194](https://doi.org/10.5281/zenodo.19323194) |
| 4 | [The Serial Decoding Basin τ](https://github.com/Windstorm-Institute/serial-decoding-basin) | [10.5281/zenodo.19323423](https://doi.org/10.5281/zenodo.19323423) |
| 5 | [The Dissipative Decoder](https://github.com/Windstorm-Institute/dissipative-decoder) | [10.5281/zenodo.19433048](https://doi.org/10.5281/zenodo.19433048) |
| 6 | [The Inherited Constraint](https://github.com/Windstorm-Institute/inherited-constraint) | [10.5281/zenodo.19432911](https://doi.org/10.5281/zenodo.19432911) |
| 7 | [The Throughput Basin Origin](https://github.com/Windstorm-Institute/throughput-basin-origin) | [10.5281/zenodo.19498582](https://doi.org/10.5281/zenodo.19498582) |
| 8 | [The Vision Basin](https://github.com/Windstorm-Institute/vision-basin) | [10.5281/zenodo.19672827](https://doi.org/10.5281/zenodo.19672827) |
| 9 | [The Hardware Basin](https://github.com/Windstorm-Institute/hardware-basin) *(this paper)* | [10.5281/zenodo.19672921](https://doi.org/10.5281/zenodo.19672921) |

### Track 2 — Entropic Bounds in Analog Systems · 7 papers (Papers 10–16; line of inquiry active)

| # | Paper | DOI |
|---|-------|-----|
| 10 | [Phonon Extraction Bound (BEC Analog Gravity)](https://github.com/Windstorm-Institute/phonon-extraction-bound) | [10.5281/zenodo.20014391](https://doi.org/10.5281/zenodo.20014391) |
| 11 | [Gravitational Entropy Escrow](https://github.com/Windstorm-Institute/gravitational-entropy-escrow) | [10.5281/zenodo.20032023](https://doi.org/10.5281/zenodo.20032023) |
| 12 | [C8 Clarification Note](https://github.com/Windstorm-Institute/c8-clarification-note) | [10.5281/zenodo.20041992](https://doi.org/10.5281/zenodo.20041992) |
| 13 | [Lattice QFT Test of the Static Escrow Postulate](https://github.com/Windstorm-Institute/lattice-qft-test) *(4th in track; supplement to Paper 11)* | [10.5281/zenodo.20057538](https://doi.org/10.5281/zenodo.20057538) |
| 14 | [Spacetime as Escrow Bookkeeping](https://github.com/Windstorm-Institute/escrow-spacetime) *(5th in track; translation of standard GR results into the escrow vocabulary; companion to Paper 11)* | [10.5281/zenodo.20126091](https://doi.org/10.5281/zenodo.20126091) |
| 15 | [The 𝒩<sub>esc</sub> Recipe](https://github.com/Windstorm-Institute/nesc-recipe) *(6th in track; formalizes 𝒩<sub>esc</sub> as a cross-regime function; continuation of Paper 14)* | [10.5281/zenodo.20145106](https://doi.org/10.5281/zenodo.20145106) |
| 16 | [The Compton Corollary](https://github.com/Windstorm-Institute/compton-corollary) *(7th in track; short Bekenstein observation at the Compton scale; uses 𝒩<sub>esc</sub> notation only, escrow recipe not invoked)* | [10.5281/zenodo.20163451](https://doi.org/10.5281/zenodo.20163451) |

**Website:** [windstorminstitute.org](https://windstorminstitute.org)

---

*Code: MIT License · Data: CC BY 4.0*

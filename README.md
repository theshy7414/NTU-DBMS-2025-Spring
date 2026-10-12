# OutfitMatch V2 — Research Track (SHIFT15M)

**Detecting Unreliable Fashion Matching Predictions under Temporal Distribution Shift.**

Time-boxed research line of OutfitMatch V2 (NTU DBMS project). The previous v1 project is preserved at tag `v1-final`.

## Contents

| Path | What |
|---|---|
| `EXPERIMENT1_SPEC.md` | Experiment 1 specification (item-FITB under temporal shift, gates, amendments) |
| `EXPERIMENT2_PREREG.md` | Experiment 2 pre-registration (reliability / error detection), written before any score was computed |
| `step0/manifests/` | Frozen split and evaluation-instance manifests (`MANIFEST_SHA256.txt`) |
| `step0/scripts/` | All pipeline scripts (`50`-`53` Experiment 1 training, `60`-`63` Experiment 2) |
| `step0/results/` | Text reports and instance-level tables |
| `step0/runs/` | Logs, predictions, confidence scores, figures, reproduction notes (`REPRODUCE.md`, `EXP2_REPRODUCE.md`) |

## Not in this repository

VGG16 features and anything derived from the SHIFT15M/IQON images (CC BY-NC), model checkpoints (`*.pt`), the vendored Python libs, and bootstrap pickles. They can be regenerated with the scripts and commands in `step0/runs/REPRODUCE.md` and `step0/runs/EXP2_REPRODUCE.md`.

## Headline result (Experiment 2)

Under temporal shift the single-model MSP error-detection AUROC drops by 0.06-0.08 (Gate 1 passed). kNN-uncertainty and ensemble mutual information do **not** beat maximum softmax probability (Gate 2 not passed); see `step0/results/exp2_gates_report.txt` and `step0/results/exp2_main_report.txt`.

**Project page:** https://www.tashrifwala.com/projects/Deepfake-detection-html-1.html

[![Hugging Face – Model](https://img.shields.io/badge/HuggingFace-Model-yellow.svg)](https://huggingface.co/Shabbir1/robust-deepfake-detector)


# Adversarially Robust Deepfake Detection

This project investigates a compact deepfake detector that remains reliable under adversarial manipulation. We propose a hybrid architecture combining an EfficientNet backbone with a small Vision Transformer head and train it using a dual attacker regime. One attacker is projected gradient descent, while the other is a tiny U Net that learns subtle, realistic perturbations shaped by total variation and frequency losses. We train on FaceForensics plus plus crops and evaluate cross dataset on Celeb DF v2. On clean inputs, the robust model matches a standard baseline, and under a combined learned attack with compression it attains a higher true positive rate at 1 percent false positive rate, a regime critical for high precision scenarios. Grad CAM analyses further indicate that the robust model attends to broader facial cues rather than narrow edge artifacts, aligning with its improved resilience.

## Key features

- Hybrid EfficientNet plus Transformer classifier for local texture and global consistency cues
- Robustness-oriented development with PGD and a learned U-Net style attacker, constrained by total variation and frequency losses
- Stress testing under compression settings such as JPEG-50 and an H.264-like setup
- Metrics used: TPR at 1% FPR, ROC-AUC and accuracy
- Grad-CAM explanations to visualize discriminative cues

## Repository contents

Only files that are part of the released artifacts are included.

```
notebooks/
  deepfake-detection-v1.ipynb
  Untitled12.ipynb

models/                     # tracked with Git LFS
  baseline_model.pth
  robust_model.pth

results/
  phase4.1/
    phase4_1_eval_results.csv
    phase4_1_eval_results.json
  phase4.2/
    metrics_summary.csv
    roc_panels.png
    gradcam/
      celeb_base_000.png
      celeb_base_001.png
      ... more celeb_base_***.png

logs/
  tensorboard/
    events.out.tfevents...
```

## Results artifacts

- **Phase 4.1**
  - `results/phase4.1/phase4_1_eval_results.csv`
  - `results/phase4.1/phase4_1_eval_results.json`
- **Phase 4.2**
  - `results/phase4.2/metrics_summary.csv`
  - `results/phase4.2/roc_panels.png`
  - `results/phase4.2/gradcam/*.png`

## Project page and report

The project page provides a readable overview and links to the full report: see the URL at the top of this README.

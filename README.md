# VFU-StressTest

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Ashhar-Hussain/VFU-StressTest/blob/main/VFU_StressTest_Pilot.ipynb)

Pilot code for the research proposal **"Stress-Testing Vertical Federated Unlearning under Party Heterogeneity, Distribution Shift, and Continued Training"** (Ashhar Hussain).

It reproduces the evaluation protocol of REMISVFU (Wu et al., AAAI 2026, [doi:10.1609/aaai.v40i32.39911](https://doi.org/10.1609/aaai.v40i32.39911)) at small scale. It then tests whether the forgetting certificate survives changed conditions.

- **Reference:** a backdoored 3-party split-VFL model; retraining without the forgotten party (gold reference); REMISVFU-style representation-misdirection unlearning with orthogonal gradient projection; a never-poisoned 3-party model.
- **Axis A, party heterogeneity:** the forgotten party is the left, centre, or right image slice.
- **Axis B, distribution shift:** shifted trigger variants (moved, larger, dimmer, other corner) and Gaussian noise on the remaining parties.
- **Axis C, continued training:** a relearning probe that fine-tunes on a small poisoned budget and records backdoor success after 10/25/50/100 steps, compared with a model that never learned the backdoor.
- **Audit:** linear-probe recovery of labels and trigger presence from the forgotten party's representation.
- **Statistics:** 5 seeds, 95% t-intervals, exact McNemar tests against retraining with Holm correction, and unlearning time as a percentage of retraining.

## Run
1. Open the notebook in Colab using the badge above, and select `Runtime → Change runtime type → T4 GPU`.
2. Select `Runtime → Run all`.
3. The mode is chosen automatically: FULL on GPU (MNIST and Fashion-MNIST, 5 seeds, 3 positions) or QUICK on CPU.

Outputs are written to `results/summary.md`, `results/raw.json`, and `results/relearning.png`.

## Protocol notes
The pilot follows the paper on the following settings: equal vertical slices, 2-layer CNN encoders (32/64 channels, 2×2 max-pooling), a top model with two FC layers (hidden size 128), a 2×2 white trigger with target label 0, about 10% poisoning, c = 1, and α = 1e-3.

The paper does not specify the optimizer, learning rate, or number of unlearning epochs. The pilot uses Adam with learning rate 1e-3, batch size 256, 5 training epochs, and 3 unlearning epochs (FULL mode).

Backdoor success follows the paper's convention: it is the share of all triggered test images predicted as the target, so a backdoor-free model sits near the class prior.

Results are preliminary.

## License
MIT

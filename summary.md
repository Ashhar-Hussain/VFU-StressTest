# VFU-StressTest pilot results (FULL mode, device: cuda)

Seeds: [0, 1, 2, 3, 4]. Values are mean ± 95% CI half-width across seeds (t-interval), in %.

## Reference comparison and Axis A (forgotten-party position)

| Dataset | Forgotten | Acc orig | Acc retrain | Acc unlearn | ASR orig | ASR unlearn | ASR natural | Unlearn time (% of retrain) | McNemar significant (Holm, p<0.05) |
|---|---|---|---|---|---|---|---|---|---|
| MNIST | centre | 98.5 ± 0.1 | 90.5 ± 0.5 | 90.2 ± 1.0 | 99.8 ± 0.2 | 38.2 ± 17.7 | 9.9 ± 0.1 | 107.1 ± 2.1 | 3/5 seeds |
| MNIST | left | 98.5 ± 0.1 | 97.5 ± 0.5 | 96.4 ± 2.1 | 100.0 ± 0.0 | 29.4 ± 21.6 | 9.9 ± 0.2 | 125.2 ± 4.8 | 2/5 seeds |
| MNIST | right | 98.5 ± 0.1 | 97.7 ± 0.2 | 98.1 ± 0.6 | 100.0 ± 0.0 | 88.4 ± 10.0 | 9.9 ± 0.1 | 106.6 ± 2.9 | 5/5 seeds |
| FashionMNIST | centre | 89.2 ± 0.7 | 85.4 ± 1.1 | 86.5 ± 0.3 | 99.2 ± 0.8 | 25.5 ± 12.8 | 10.6 ± 1.5 | 106.3 ± 2.5 | 2/5 seeds |
| FashionMNIST | left | 89.2 ± 0.8 | 88.4 ± 0.6 | 89.3 ± 0.8 | 99.3 ± 0.6 | 12.6 ± 2.0 | 11.3 ± 1.2 | 124.6 ± 4.1 | 2/5 seeds |
| FashionMNIST | right | 89.5 ± 0.6 | 88.5 ± 0.7 | 89.1 ± 1.0 | 100.0 ± 0.0 | 36.0 ± 8.5 | 10.7 ± 1.4 | 106.0 ± 2.5 | 3/5 seeds |

## Axis B: backdoor success under shifted triggers (original → unlearned)

| Dataset | Forgotten | shift1 | shift2 | size3 | dim | corner |
|---|---|---|---|---|---|---|
| MNIST | centre | 27.6 ± 8.4 → 11.7 ± 1.5 | 10.6 ± 0.6 → 11.7 ± 1.4 | 97.6 ± 2.8 → 11.9 ± 1.6 | 60.1 ± 11.8 → 11.8 ± 1.5 | 9.9 ± 0.2 → 11.7 ± 1.5 |
| MNIST | left | 18.2 ± 6.3 → 12.5 ± 2.7 | 14.4 ± 4.7 → 11.2 ± 1.7 | 98.0 ± 3.6 → 16.6 ± 5.3 | 71.7 ± 11.2 → 12.3 ± 2.2 | 9.9 ± 0.2 → 12.3 ± 2.2 |
| MNIST | right | 97.5 ± 4.4 → 10.8 ± 1.1 | 50.1 ± 16.2 → 10.8 ± 1.4 | 100.0 ± 0.0 → 17.9 ± 14.5 | 85.3 ± 9.8 → 10.5 ± 0.8 | 9.6 ± 0.3 → 10.3 ± 0.8 |
| FashionMNIST | centre | 12.3 ± 2.3 → 12.3 ± 2.7 | 10.3 ± 2.1 → 11.9 ± 2.2 | 93.9 ± 7.4 → 12.6 ± 3.1 | 49.3 ± 3.8 → 12.0 ± 2.3 | 9.5 ± 1.9 → 11.8 ± 2.2 |
| FashionMNIST | left | 12.7 ± 2.7 → 12.0 ± 2.0 | 11.0 ± 3.2 → 11.9 ± 2.0 | 87.1 ± 11.6 → 12.5 ± 1.8 | 52.2 ± 4.6 → 12.0 ± 2.0 | 10.1 ± 1.6 → 12.2 ± 1.9 |
| FashionMNIST | right | 76.9 ± 14.5 → 13.0 ± 3.5 | 16.4 ± 3.4 → 12.6 ± 2.9 | 99.6 ± 0.4 → 12.8 ± 3.5 | 92.4 ± 2.5 → 12.4 ± 2.8 | 12.5 ± 1.0 → 12.4 ± 2.8 |

## Axis B: clean accuracy under noise on the remaining parties (retrain vs. unlearned)

| Dataset | Forgotten | σ=0.2 | σ=0.4 |
|---|---|---|---|
| MNIST | centre | 69.4 ± 4.6 vs 71.5 ± 5.2 | 30.2 ± 3.5 vs 34.1 ± 8.4 |
| MNIST | left | 92.9 ± 1.7 vs 92.0 ± 4.9 | 41.6 ± 8.6 vs 40.6 ± 9.9 |
| MNIST | right | 95.9 ± 0.6 vs 96.0 ± 1.0 | 59.6 ± 7.3 vs 50.9 ± 4.8 |
| FashionMNIST | centre | 38.4 ± 11.2 vs 29.8 ± 6.2 | 17.3 ± 4.4 vs 12.7 ± 0.7 |
| FashionMNIST | left | 70.0 ± 5.5 vs 64.7 ± 8.3 | 39.0 ± 5.3 vs 37.1 ± 7.8 |
| FashionMNIST | right | 47.6 ± 5.1 vs 38.1 ± 5.4 | 18.4 ± 4.2 vs 16.8 ± 6.3 |

## Axis C: relearning probe (backdoor success after k fine-tuning steps; unlearned vs. never-poisoned)

| Dataset | Forgotten | k=0 | k=10 | k=25 | k=50 | k=100 |
|---|---|---|---|---|---|---|
| MNIST | centre | 38.2 ± 17.7 vs 9.9 ± 0.1 | 81.0 ± 15.6 vs 15.5 ± 2.5 | 98.0 ± 3.7 vs 22.4 ± 3.8 | 99.8 ± 0.2 vs 30.2 ± 7.9 | 99.7 ± 0.2 vs 78.5 ± 6.7 |
| MNIST | left | 29.4 ± 21.6 vs 9.9 ± 0.2 | 99.2 ± 1.0 vs 16.4 ± 2.7 | 99.9 ± 0.2 vs 35.2 ± 7.1 | 99.7 ± 0.3 vs 68.0 ± 9.8 | 99.9 ± 0.1 vs 92.7 ± 3.1 |
| MNIST | right | 88.4 ± 10.0 vs 9.9 ± 0.1 | 99.6 ± 0.3 vs 16.6 ± 2.9 | 99.8 ± 0.1 vs 33.3 ± 7.6 | 99.9 ± 0.1 vs 74.9 ± 10.8 | 100.0 ± 0.0 vs 94.8 ± 3.9 |
| FashionMNIST | centre | 25.5 ± 12.8 vs 10.6 ± 1.5 | 70.3 ± 13.0 vs 14.6 ± 3.7 | 95.7 ± 2.8 vs 20.8 ± 9.0 | 97.1 ± 4.2 vs 25.1 ± 12.5 | 97.4 ± 1.4 vs 61.6 ± 12.9 |
| FashionMNIST | left | 12.6 ± 2.0 vs 11.3 ± 1.2 | 72.0 ± 11.0 vs 16.0 ± 3.6 | 98.6 ± 0.9 vs 26.1 ± 10.3 | 99.0 ± 1.0 vs 47.4 ± 7.6 | 98.1 ± 1.3 vs 81.0 ± 8.3 |
| FashionMNIST | right | 36.0 ± 8.5 vs 10.7 ± 1.4 | 82.1 ± 11.7 vs 16.9 ± 5.9 | 99.4 ± 0.5 vs 29.7 ± 17.2 | 99.8 ± 0.2 vs 59.3 ± 12.4 | 99.7 ± 0.2 vs 94.2 ± 3.0 |

## Representation audit: linear-probe accuracy on the forgotten party's representation (original → unlearned)

| Dataset | Forgotten | Label probe | Trigger probe (chance = 50) |
|---|---|---|---|
| MNIST | centre | 91.9 ± 1.2 → 27.3 ± 9.9 | 100.0 ± 0.0 → 73.5 ± 6.8 |
| MNIST | left | 63.8 ± 1.6 → 12.7 ± 1.7 | 100.0 ± 0.1 → 95.3 ± 3.7 |
| MNIST | right | 60.2 ± 1.2 → 16.2 ± 1.7 | 100.0 ± 0.1 → 99.6 ± 0.3 |
| FashionMNIST | centre | 76.4 ± 1.0 → 31.8 ± 9.1 | 99.9 ± 0.1 → 78.5 ± 11.9 |
| FashionMNIST | left | 76.8 ± 0.7 → 18.0 ± 6.9 | 99.8 ± 0.1 → 75.8 ± 6.8 |
| FashionMNIST | right | 75.8 ± 2.0 → 23.7 ± 7.8 | 100.0 ± 0.0 → 83.8 ± 2.5 |

Notes: ASR follows the REMISVFU convention (share of all triggered test images predicted as the target label), so a backdoor-free model sits near the class prior (see "ASR natural"). Retraining removes the forgotten slice, so its representation probes are at chance by construction. Pilot settings not given in the paper: Adam (lr 1e-3), batch 256.
# ZT-TrustFed

**ZT-TrustFed: A Trust-Aware Federated Intrusion Detection Framework for Heterogeneous and Non-IID Security Data**

ZT-TrustFed is a trust-based federated learning system for intrusion detection that integrates:

* FedProx regularization
* Dynamic trust-based weighted aggregation (T-Krum)
* Gaussian differential privacy
* Single-step adversarial training (FGSM)
* Zero-Trust client filtering
* Ledger-based auditability

The framework is evaluated on three heterogeneous benchmark datasets (CIC-IoT2023, CIC-IDS2017, and BoT-IoT) after feature alignment to a common 25-dimensional representation.

## Requirements

* Python 3.10+
* Google Colab or Jupyter Notebook

Install the required packages:

```bash
pip install -r requirements.txt
```

## Implementation

The complete experimental implementation is available as a Google Colab notebook:

**https://colab.research.google.com/drive/1FxUYGA5Nj6BcSbt4jE-6C1fVyVlzgvRP?usp=sharing**

A local copy of the pipeline notebook can be placed here as `ZT_TrustFed_complete_pipeline.ipynb` once exported from Colab.

The notebook contains the complete experimental implementation, including data preprocessing, federated training, baselines, ablation studies, Byzantine resilience tests, privacy–utility analysis, adversarial robustness evaluation, scalability experiments, statistical analysis, and visualization.

## Repository Structure

```text
ZT_TrustFed/
├── ZT_TrustFed_complete_pipeline.ipynb   # (export from Colab)
├── requirements.txt
├── README.md
├── results/
│   ├── summary_metrics.csv
│   ├── ablation_results.csv
│   └── byzantine_results.csv
├── figures/
│   ├── fig1_system_architecture.png
│   ├── fig2_tkrum_architecture.png
│   ├── fig3_convergence.png
│   ├── fig4_perclient_accuracy.png
│   ├── fig5_perclient_bacc.png
│   ├── fig6_perclient_macrof1.png
│   ├── fig7_ablation_macrof1.jpeg
│   ├── fig8_ablation_bacc.jpeg
│   ├── fig9_privacy_utility.png
│   ├── fig10_heatmap_metrics.png
│   ├── fig11_confusion_matrices.png
│   ├── fig12_roc_curves.png
│   ├── fig13_classwise_performance.png
│   ├── fig14_trust_weight_evolution.png
│   ├── fig15_byzantine_robustness.jpeg
│   └── fig16_scalability.jpeg
```

## Results

The `results/` directory contains key experimental summary tables extracted from the manuscript. The `figures/` directory contains the generated visualizations from the paper.

Key client-level performance (final model):

| Client   | Accuracy | Balanced Accuracy | Macro-F1 | ROC-AUC |
|----------|----------|-------------------|----------|---------|
| CIC23    | 0.9534   | 0.9701            | 0.7297   | 0.9905  |
| CIC17    | 0.8938   | 0.9428            | 0.6434   | 0.9789  |
| BOT      | 0.9999   | 0.5000            | 0.5000   | 0.5000  |

## Reproducibility

Experiments use fixed random seeds (including 2024–2028 for multi-seed Byzantine runs). The implementation was developed and tested using Python 3.10+ and Google Colab / PyTorch.

## Authors

**Saumya Mishra**  
Original implementation and experimental work.

**Wejdan Ali Almutiri**  
Methodology, validation, review, and editing.

**Shailendra Mishra**  
Supervision.

## Citation

The DOI and final publication information will be added after the research is formally deposited via Zenodo / GitHub release.

## Data Availability

The datasets analyzed in this study are publicly available:

* CIC-IDS-2017: https://www.kaggle.com/datasets/chethuhn/network-intrusion-dataset
* CIC IoT 2023: https://www.kaggle.com/datasets/akashdogra/cic-iot-2023
* BoT-IoT: https://www.kaggle.com/datasets/vigneshvenkateswaran/bot-iot

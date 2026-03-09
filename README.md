# Federated Learning-Based Privacy-Preserving Ransomware Detection

## Project Summary

Ransomware is a rapidly evolving malware threat that encrypts user data and demands ransom, causing widespread damage to critical infrastructure and services. Effective detection requires large and diverse datasets, but organizations often cannot share sensitive logs or malware samples due to privacy and regulatory constraints. This isolation of data severely limits model performance.

To address this, we propose a **federated learning (FL) framework** for ransomware detection where multiple clients (e.g., different organizations) train local models on their private data and share only model updates with a central server. The server aggregates these updates (e.g., using FedAvg or secure multi-task methods) and produces a global model that benefits from all data without ever exchanging raw data.

Our system uses both **feature-based (EMBER)** and **image-based (Malimg)** datasets to build a hybrid multi-modal detection model. Each simulated client trains an appropriate local model (MLP for EMBER features, CNN for Malimg images). The central aggregator combines these heterogeneous models via ensemble or FedMD-style distillation and distributes an improved global model back to clients.

---

## Key Features

- 🔒 **Privacy-preserving Federated Learning** — raw data never leaves the client
- 🧠 **Hybrid multi-modal detection** — image-based + feature-based approaches combined
- 🖼️ **CNN for Malimg** — image classification of malware binary visualizations
- 📊 **MLP for EMBER** — feature-based malware classification using PE file features
- 🔄 **FedAvg / FedMD aggregation algorithms** — handles heterogeneous models
- 📈 **Interactive visualization dashboard** with SHAP/LIME explainability

---

## Tech Stack

| Category | Technologies |
|---|---|
| Language | Python 3.10+ |
| Deep Learning | TensorFlow / Keras |
| Federated Learning | Flower (flwr) |
| Dashboard | Streamlit / Flask |
| ML Utilities | scikit-learn, NumPy, Pandas |
| Visualization | Matplotlib, Seaborn |
| Explainability | SHAP, LIME |

---

## Project Structure

```
FL-ransomware-detection/
├── data/
│   └── README.md               # Dataset sources & download instructions (EMBER & Malimg)
├── notebooks/                  # Jupyter/Colab notebooks for exploration & experiments
├── models/                     # Saved model files (excluded from version control)
├── src/
│   ├── malimg/                  # CNN work for Malimg image-based detection
│   ├── ember/                   # MLP work for EMBER feature-based detection
│   └── federated/               # Flower FL framework code
├── dashboard/                   # Streamlit/Flask visualization dashboard
├── docs/                        # Documentation & reports
├── .gitignore
├── requirements.txt
└── README.md
```

---

## Datasets

- **Malimg Dataset** — Image-based malware visualization dataset (~9,339 images, 25 malware families). Grayscale images representing malware binaries. Used with the CNN model.
  - 📥 [Download from Kaggle](#) *(link to be added)*
- **EMBER Dataset** — Feature-based malware dataset with extracted PE file features. Used with the MLP model.
  - 📥 [Download here](#) *(link to be added)*

See [`data/README.md`](data/README.md) for detailed download and setup instructions.

---

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/NARMEEN-UROOJ/FL-ransomware-detection.git
cd FL-ransomware-detection
```

### 2. Create a virtual environment

```bash
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate
```

### 3. Install requirements

```bash
pip install -r requirements.txt
```

### 4. Download datasets

Follow the instructions in [`data/README.md`](data/README.md) to download and place the EMBER and Malimg datasets in the correct directories.

---

## Team

| Name | GitHub |
|---|---|
| Narmeen Urooj | [@NARMEEN-UROOJ](https://github.com/NARMEEN-UROOJ) |
| Muhammad Asad | [@Muhammadasad29](https://github.com/Muhammadasad29) |

---

## License

This project is for academic purposes as part of a Final Year Project (FYP). License to be determined.
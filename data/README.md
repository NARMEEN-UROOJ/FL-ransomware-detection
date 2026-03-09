# Datasets

This directory contains dataset download instructions and preprocessing notes. Actual data files are **excluded from version control** via `.gitignore`.

---

## Malimg Dataset

**Description:** Image-based malware visualization dataset containing grayscale images that represent malware binaries as 2D images. Each image corresponds to a malware sample from one of 25 malware families.

- **Size:** ~9,339 images
- **Classes:** 25 malware families
- **Format:** Grayscale PNG/BMP images
- **Model:** Used with the CNN model (`src/malimg/`)
- 📥 **Download:** [Malimg on Kaggle](#) *(link to be added)*

### Download & Setup

1. Download the Malimg dataset from Kaggle (link above)
2. Extract the zip file
3. Place the extracted folder at `data/malimg/` so the structure looks like:

```
data/malimg/
├── Adialer.C/
├── Agent.FYI/
├── Allaple.A/
├── ...
└── Yuner.A/
```

---

## EMBER Dataset

**Description:** Feature-based malware dataset with extracted PE (Portable Executable) file features. Includes both malware and benign samples with rich feature sets derived from file headers, imports, exports, and other static analysis signals.

- **Format:** JSON / numpy arrays with pre-extracted features
- **Model:** Used with the MLP model (`src/ember/`)
- 📥 **Download:** [EMBER Dataset](#) *(link to be added)*

### Download & Setup

1. Download the EMBER dataset from the link above
2. Extract the dataset
3. Place the files at `data/ember/` so the structure looks like:

```
data/ember/
├── train_features_0.jsonl
├── train_features_1.jsonl
├── ...
├── test_features.jsonl
└── metadata.csv
```

---

## Notes

- All data files (`.zip`, `.csv`, `.pkl`) and dataset directories (`data/malimg/`, `data/ember/`) are excluded from version control via `.gitignore`
- Never commit raw dataset files to this repository
- Each team member must download the datasets locally following the instructions above

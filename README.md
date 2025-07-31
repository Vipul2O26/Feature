
# 🔬 Identification and Classification of Fungal Adhesive and Non-Adhesive Proteins Using Machine Learning

This project presents a machine learning pipeline to identify and classify fungal adhesive and non-adhesive proteins using ensemble techniques and sequence-based features.

---

## 📌 Project Overview

Fungal adhesins play a key role in host attachment, biofilm formation, and pathogenesis. Predicting them computationally enables rapid screening and functional annotation. This project follows a multi-step machine learning workflow involving:

- Sequence collection and preprocessing  
- Redundancy removal (CD-HIT)  
- Feature extraction (R Studio)  
- Classification and evaluation (WEKA)

---

## 🧪 Tools & Technologies

- **CD-HIT v4.8.1** – Redundancy removal  
- **R Studio** – Feature extraction using `protr`, `Peptides`, and `foreign` libraries  
- **WEKA GUI** – Model training, classification, and evaluation  
- **Language** – R

---

## 🔬 Methodology

### 1. Data Collection
- Collected 200 adhesive and 600 non-adhesive protein sequences.
- Saved as `Positive.fasta` and `Negative.fasta`.

### 2. Redundancy Removal (CD-HIT)
- **Command**:
  ```bash
  cd-hit -i Positive.fasta -o Positive_NR -c 0.8 -n 5
  ```
- Removes sequences with ≥80% identity to ensure non-redundant data.

### 3. Feature Extraction (R Studio)
- Features extracted:
  - **AAC** – Amino Acid Composition
  - **APAAC** – Amphiphilic Pseudo-AAC
  - **CTDC, CTDD, CTDT** – Composition, Distribution, and Transition of grouped properties
  - **DC** – Dipeptide Composition
  - **TC** – Tripeptide Composition
- Output saved as `.csv` and `.arff` for use in WEKA.

### 4. Classification (WEKA)
- Classifiers used:
  - SMO (SVM)
  - Naive Bayes
  - J48
  - Random Forest
- Dataset split:
  - 80/20 training/testing split
  - 5-fold and 10-fold cross-validation
- Evaluation Metrics:
  - Accuracy, AUC, TPR, FPR, MCC
- Visualizations:
  - Scatter plots
  - Attribute histograms

---

## 🔎 Results Summary

- **Best Performance**:
  - Tripeptide Composition + SMO classifier
  - Dipeptide Composition + Naive Bayes also showed strong results
- CD-HIT clustering improved data quality.
- Visualizations confirmed effective class separation using selected features.

---

## 📈 Final Workflow

```
FASTA → CD-HIT → R Studio (Features) → ARFF → WEKA → Model Evaluation
```

---

## 📁 Project Structure

```
├── Positive.fasta / Negative.fasta
├── CD-HIT clustered output
├── R scripts for feature extraction
├── .csv and .arff feature files
├── WEKA project files and results
└── Report.docx
```

---

## 📚 References

1. Li W, Godzik A. *CD-HIT: A fast program for clustering and comparing large sets of protein sequences*. Bioinformatics.  
2. Xiao N et al. *protr: R package for generating numerical representations of protein sequences*.  
3. WEKA Documentation, University of Waikato.  
4. CBIRT dataset and experimental protocols.

---

## 🙏 Acknowledgements

- **Dr. Nadia** – For guidance in bioinformatics and machine learning.  
- **Dr. Tammana** – For mentorship and resources throughout the project.  
- **CBIRT Team** – For the internship opportunity and training support.

---

## 🚀 Future Scope

- Incorporate structural or evolutionary features.  
- Experiment with deep learning and hybrid models.  
- Extend dataset to include diverse fungal species.

---

## 🔗 License

This project was completed as part of an internship at the Centre for Bioinformatics Research and Technology (CBIRT).  
Usage and sharing should credit the original author and CBIRT.

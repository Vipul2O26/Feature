# Feature
# Identification and Classification of Fungal Adhesive and Non-Adhesive Proteins Using Machine Learning

This project focuses on building a machine learning pipeline to identify and classify fungal adhesive and non-adhesive proteins using ensemble techniques and sequence-based features.

## 📌 Project Overview

Fungal adhesins play a key role in host attachment, biofilm formation, and pathogenesis. Predicting them computationally enables rapid screening and functional annotation. This project utilizes a multi-step machine learning workflow with the following stages:

- Sequence collection and preprocessing
- Redundancy removal (CD-HIT)
- Feature extraction (R Studio)
- Classification and evaluation (WEKA)

---

## 🧪 Tools & Technologies

- **CD-HIT v4.8.1** – Redundancy removal
- **R Studio** – Feature extraction using `protr`, `Peptides`, and `foreign` libraries
- **WEKA GUI** – Model training, classification, evaluation
- **Programming Language** – R

---

## 🔬 Methodology

### 1. Data Collection
- 200 adhesive and 600 non-adhesive protein sequences collected from published datasets.
- Saved as `Positive.fasta` and `Negative.fasta`.

### 2. Redundancy Removal
- **Tool**: CD-HIT
- **Command**:
  ```bash
  cd-hit -i Positive.fasta -o Positive_NR -c 0.8 -n 5



Purpose: Remove sequences with ≥80% similarity.

3. Feature Extraction
Features extracted using R:

AAC – Amino Acid Composition

APAAC – Amphiphilic Pseudo-AAC

CTDC, CTDD, CTDT – Composition, Distribution, Transition of grouped properties

DC – Dipeptide Composition

TC – Tripeptide Composition

Output saved as .csv and .arff for use in WEKA.

4. Classification (WEKA)
  Classifiers used:

  SMO (SVM)

  Naive Bayes

  J48

  Random Forest

  Techniques:

  80/20 train-test split

5-fold and 10-fold cross-validation

  Evaluation metrics:

  Accuracy, AUC, TPR, FPR, MCC

  Scatter plots, attribute histograms

  🔎 Results Summary
  Best Performance:

  Tripeptide Composition + SMO classifier

  Dipeptide Composition + Naive Bayes also showed strong results

  Visualizations confirm effective separation of classes using selected features.

CD-HIT clustering helped improve data quality.

📈 Final Workflow
java
Copy
Edit
FASTA → CD-HIT → R Studio (Features) → ARFF → WEKA → Model Evaluation
📁 Project Structure
mathematica
Copy
Edit
├── Positive.fasta / Negative.fasta
├── CD-HIT clustered output
├── R scripts for feature extraction
├── .csv and .arff feature files
├── WEKA project files and results
└── Report.docx
📚 References
Li W, Godzik A. CD-HIT: A fast program for clustering and comparing large sets of protein sequences. Bioinformatics.

Xiao N et al. protr: R package for generating numerical representations of protein sequences.

WEKA Documentation, University of Waikato.

CBIRT dataset and experimental protocols.

🙏 Acknowledgements
Dr. Nadia – For guidance in bioinformatics and ML.

Dr. Tammana – For providing resources and mentorship.

CBIRT Team – For internship opportunity and training environment.

📌 Future Scope
Incorporate structural or evolutionary features.

Experiment with deep learning models.

Extend to more diverse fungal species.

🔗 License
This project was completed as part of an internship at the Centre for Bioinformatics Research and Technology (CBIRT). Usage should credit the original authors and CBIRT.


# Case-Based Reasoning (CBR) for Wanprestasi Cases at PN Sidoarjo

## Project Description

This project implements a Case-Based Reasoning (CBR) system for civil court decisions related to **Wanprestasi** cases from **Pengadilan Negeri Sidoarjo**.

The system uses:

* OCR (RapidOCR)
* TF-IDF Vectorization
* Cosine Similarity
* Case-Based Reasoning (CBR)

The objective is to retrieve the most similar previous cases and provide a predicted solution based on historical court decisions.

---

## Dataset

Source: Pengadilan Negeri Sidoarjo (Direktori Putusan Mahkamah Agung)

Domain: Wanprestasi

Number of Cases: 31 Cases

---

## Project Structure

```text
CBR-Wanprestasi-PN-Sidoarjo/
│
├── data/
│   ├── raw/
│   ├── processed/
│   ├── results/
│   └── eval/
│
├── notebooks/
│   ├── 01_case_base.ipynb
│   ├── 02_case_representation.ipynb
│   ├── 03_retrieval.ipynb
│   ├── 04_predict.ipynb
│   └── 05_evaluation.ipynb
│
├── requirements.txt
└── README.md
```

---

## Installation

### Clone Repository

```bash
git clone <repository_url>
cd CBR-Wanprestasi-PN-Sidoarjo
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Requirements

Libraries used in this project:

```text
pandas
numpy
scikit-learn
jupyter
matplotlib
pymupdf
rapidocr-onnxruntime
pillow
openpyxl
```

---

## Running the Pipeline (End-to-End)

Run the notebooks sequentially:

### Step 1 – Case Base Construction

Open:

```text
notebooks/01_case_base.ipynb
```

Functions:

* Read PDF decisions
* OCR extraction
* Text cleaning
* Create `cases.csv`

Output:

```text
data/processed/cases.csv
```

---

### Step 2 – Case Representation

Open:

```text
notebooks/02_case_representation.ipynb
```

Functions:

* Extract case number
* Extract plaintiff (penggugat)
* Extract defendant (tergugat)
* Extract decision summary

Output:

```text
data/processed/cases_final.csv
```

---

### Step 3 – Retrieval

Open:

```text
notebooks/03_retrieval.ipynb
```

Functions:

* TF-IDF vectorization
* Cosine Similarity computation
* Top-K similar case retrieval

Example query:

```text
Tergugat tidak memenuhi kewajiban pembayaran sesuai perjanjian sehingga penggugat mengalami kerugian.
```

Output:

Top 5 most similar cases.

---

### Step 4 – Prediction

Open:

```text
notebooks/04_predict.ipynb
```

Functions:

* Retrieve similar cases
* Predict solution based on the most relevant case

Output:

```text
data/results/predictions.csv
```

---

### Step 5 – Evaluation

Open:

```text
notebooks/05_evaluation.ipynb
```

Functions:

* Evaluate retrieval performance
* Calculate Accuracy
* Calculate Precision
* Calculate Recall
* Calculate F1-Score

Output:

```text
data/eval/retrieval_metrics.csv
data/eval/queries_result.csv
```

---

## Evaluation Metrics

The system is evaluated using:

* Accuracy
* Precision
* Recall
* F1-Score

---

## Methodology

The project follows the Case-Based Reasoning (CBR) cycle:

1. Retrieve
2. Reuse
3. Revise
4. Retain

Similarity between cases is computed using TF-IDF and Cosine Similarity.

---

## Author

Maulana Bima Hedy Pratama (202310370311123)
Novita Dian Nazarina (202310370311395)

Informatics Engineering

Universitas Muhammadiyah Malang

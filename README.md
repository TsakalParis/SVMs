# Cancer Classification using Support Vector Machines

A machine learning project that uses Support Vector Machines (SVMs) for multi-class classification of different cancer types based on gene expression RNA-sequencing data.

## Overview

This project demonstrates the application of SVMs to solve the classic "small n, large p" problem in genomics, where the number of features (genes) far exceeds the number of samples. Using gene expression data from The Cancer Genome Atlas (TCGA), we successfully classify five different cancer types with high accuracy.

## Cancer Types Analyzed

- **BRCA**: Breast Invasive Carcinoma - a form of breast cancer
- **LUAD**: Lung Adenocarcinoma - a common type of non-small cell lung cancer
- **KIRC**: Kidney Renal Clear Cell Carcinoma - a type of kidney cancer
- **COAD**: Colon Adenocarcinoma - a form of colon cancer
- **PRAD**: Prostate Adenocarcinoma - a type of prostate cancer

## Dataset

The dataset consists of gene expression profiles from RNA-sequencing of tumor samples:
- 801 samples across 5 cancer types
- 20,531 features (genes) per sample
- No missing values

## Methodology

### Model Selection
We chose SVMs for this classification task because they are:
- Effective in high-dimensional spaces
- Memory efficient
- Versatile and able to handle non-linearity
- Robust against overfitting in high dimensional spaces

### Implementation Details
- Linear SVM implementation (LinearSVC) for efficient handling of many features
- Grid search cross-validation for hyperparameter tuning (C parameter)
- Stratified K-fold cross-validation to maintain class distribution
- Standard scaling of features for optimal SVM performance

## Results

The model achieved perfect classification on the test set:
- **100% accuracy** across all cancer types
- **100% precision and recall** for each class
- Perfect separation of the five cancer types based solely on gene expression patterns

### Confusion Matrix
The confusion matrix shows flawless classification with no misclassified samples.

### Performance Metrics by Class
| Class | Precision | Recall | F1-Score |
|-------|-----------|--------|----------|
| BRCA  | 1.0       | 1.0    | 1.0      |
| COAD  | 1.0       | 1.0    | 1.0      |
| KIRC  | 1.0       | 1.0    | 1.0      |
| LUAD  | 1.0       | 1.0    | 1.0      |
| PRAD  | 1.0       | 1.0    | 1.0      |

## Requirements

```
numpy
pandas
scikit-learn
matplotlib
seaborn
time
```

## Installation

```bash
# Clone this repository
git clone https://github.com/username/cancer-classification-svm.git

# Navigate to the project directory
cd cancer-classification-svm

# Install required packages
pip install numpy pandas scikit-learn matplotlib seaborn
```

## Usage

The main analysis is contained in a Jupyter notebook:

```bash
jupyter notebook svm_cancer_rna_seq.ipynb
```

## File Structure

```
cancer-classification-svm/
├── cell_data.csv                    # Gene expression data
├── cell_label.csv                   # Cancer type labels
├── confusion_matrix_no_reduction.png # Visualization of results
├── svm_cancer_rna_seq.ipynb         # Main notebook
└── README.md
```

## Conclusion

The perfect classification results demonstrate that:

1. Cancer types have distinct molecular signatures that can be detected through gene expression patterns
2. SVMs are highly effective for classification tasks in high-dimensional genomic data
3. Dimensionality reduction may not be necessary when using SVMs for this type of data

These findings have potential applications in cancer diagnostics and precision medicine, where accurate classification of cancer types is crucial for treatment decisions.

## Future Work

- Apply the model to new, unseen cancer samples
- Implement feature selection to identify the most important genes for classification
- Explore non-linear kernels for potentially improved performance on more complex datasets
- Extend the model to classify cancer subtypes within each major cancer type

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- The Cancer Genome Atlas (TCGA) for providing the original gene expression data
- The scikit-learn team for their implementation of SVM algorithms

# Sparse Convolutional Denoising Autoencoders for Genotype Imputation
Genotype imputation, where missing genotypes can be computationally imputed, is an essential tool in genomic analysis ranging from genome wide associations to phenotype prediction. Traditional genotype imputation methods are typically based on Hidden Markov Models (HMMs) and are usually computationally expensive. Deep learning-based methods have been recently reported to nicely address the missing data problems in various fields. To explore the performance of deep learning for genotype imputation, in this study we propose a deep model called a Sparse Convolutional Denoising Autoencoder (SCDA) to impute missing genotypes. We constructed the SCDA model by using a convolutional layer that can extract various correlation or linkage patterns in the genotype data and applying a sparse weight matrix resulted from the L1 regularization to handle high dimensional data. We comprehensively evaluated the performance of the SCDA model in different scenarios for genotype imputation on the yeast and human genotype data respectively. Our results showed that SCDA has strong robustness and significantly outperforms three popular reference-free imputation methods including row average, k-nearest neighbors and singular-value decomposition. This study thus points to another novel application of deep learning models for missing data imputation in genomic studies. 



## Getting Started
These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites
```
Python3.6 
virtualenv >= 16.4.3
```

### Setup
Create virtual environment
```
git clone https://github.com/shilab/SCDA.git
cd SCDA
mkdir venv
python3 -m venv venv/
source venv/bin/activate
```

Install requirment dependents
```
pip install tensorflow sklearn pandas jupyter matplotlib
```

### Running
1. Unzip the data files in data folder
2. Launch Jupyter notebook
```
jupyter notebook
```


## Citation
Junjie Chen, Xinghua Shi\*. Sparse Convolutional Denoising Autoencoders for Genotype Imputation. *Genes*, 2019.
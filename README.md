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

## Case study
To demonstrate the SCDA's usage for practical purpose, we provide a case study for yeast genotype imputation.

1. Input file format
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right">
      <th></th>
      <th>33070_chrI_33070_A_T</th>
      <th>33147_chrI_33147_G_T</th>
      <th>33152_chrI_33152_T_C</th>
      <th>33200_chrI_33200_C_T</th>
      <th>33293_chrI_33293_A_T</th>
      <th>33328_chrI_33328_C_A</th>
      <th>33348_chrI_33348_G_C</th>
      <th>33403_chrI_33403_C_T</th>
      <th>33502_chrI_33502_A_G</th>
      <th>33548_chrI_33548_A_C</th>
      <th>...</th>
      <th>12048853_chrXVI_925593_G_C</th>
      <th>12049199_chrXVI_925939_T_C</th>
      <th>12049441_chrXVI_926181_C_T</th>
      <th>12050613_chrXVI_927353_T_G</th>
      <th>12051167_chrXVI_927907_A_C</th>
      <th>12051240_chrXVI_927980_A_G</th>
      <th>12051367_chrXVI_928107_C_T</th>
      <th>12052782_chrXVI_929522_C_T</th>
      <th>12052988_chrXVI_929728_A_G</th>
      <th>12053130_chrXVI_929870_C_T</th>
    </tr>
    <tr>
      <th>SAMID</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>01_01</th>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>...</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
    </tr>
    <tr>
      <th>01_02</th>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>...</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
    </tr>
    <tr>
      <th>01_03</th>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>...</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
    </tr>
    <tr>
      <th>01_04</th>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>...</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
    </tr>
    <tr>
      <th>01_06</th>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>...</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
    </tr>
  </tbody>
</table>


## Citation
Junjie Chen, Xinghua Shi\*. Sparse Convolutional Denoising Autoencoders for Genotype Imputation. *Genes*, 2019.
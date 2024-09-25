# A self-attention driven deep leaning framework for inference of transcriptional gene regulatory networks


This repository contains code, data, tables and plots to support data analyses and reproduce results from the paper Distribution-agnostic Deep Learning Enables Accurate Single‐Cell Data Imputation and Transcriptional Regulation Interpretation.
- [Abstract](#abstract)
- [Overview](#overview)
- [System Requirements](#system-requirements)
- [Installation Guide](#installation-guide)


# Abstract
The interactions between transcription factors (TFs) and the target genes could provide basis for constructing gene regulatory networks (GRNs) that modulate biological processes during development of biological cells or progressions of disease. From gene expression data, particularly single-cell transcriptomes contain rich cell-to-cell variations, it is a highly desirable to infer TF-gene interactions (TGIs) using deep learning technologies. Numerous models or software including deep leaning-based algorithms have been designed to identify transcriptional regulatory relationships between TFs and the downstream genes. However, these methods do not significantly improve predictions of GRNs due to some limitations regarding constructing underlying interactive structure linking regulatory components. In this study, we introduce a deep learning framework DeepTGI that could identify TGIs and infer the GRNs with superior performance. The DeepTGI approach encodes gene expression profiles using auto-encoder with self-attention mechanism, transforms multi-head attention modules to train the model and to predict TGIs. We evaluated DeepTGI performance by comparing with other methods using different expression datasets, cell linages and species. The comparative analysis demonstrates the superiority of DeepTGI in capturing more potential TGIs, that provide broader perspectives for discovery of more gene-gene relationships that form more biological meaningful networks.

# Overview
<div align=center>
<img src="https://github.com/yyj971117/DeepTGI/blob/main/Overview.png" height="600" width="800">
</div>

# System Requirements
## Hardware requirements
`DeepTGI` requires only a standard computer with enough RAM to support the in-memory operations.

## Software requirements
### OS Requirements
This package is supported for *Linux*. The package has been tested on the following systems:
+ Linux: Ubuntu 18.04

### Python Dependencies
`DeepTGI` mainly depends on the Python scientific stack.
```
numpy
scipy
torch
pytorch-lightning
scikit-learn
pandas
scanpy
anndata
tensorboardX
pytorchtools
```
For specific setting, please see <a href="https://github.com/yyj971117/DeepTGI/blob/main/environment.yml">requirement</a>.

# Installation Guide
```
$ git clone https://github.com/yyj971117/DeepTGI.git
$ conda env create -f environment.yml
$ conda activate deepTGI
```
# Detailed tutorials with example datasets
`DeepTGI` is a deep learning framework that utilizes autoencoders and multi-head attention mechanisms to accurately identify interactions between transcription factors and genes and infer gene regulatory networks.

The example can be seen in the <a href="https://github.com/yyj971117/DeepTGI/tree/main/DeepTGI/program/main.py">main.py</a>.

# DeepTGI

DeepTGI Model

## Quick Start (Tested on Linux)

  * Clone deepTGI repository
```
git clone https://github.com/yyj971117/DeepTGI.git
```
  * Go to deepTGI repository
```
cd deepTGI
```
  * Create conda environment
```
conda env create -f environment.yml
```
  * activate deepTGI environment
```
conda activate deepTGI
```
 * Extract model files
   > Before running the program, you need to extract the model files from the split archives located in /DeepTGI/test_R. Use the following command to extract the files：
```
sudo apt-get update
sudo apt-get install p7zip-full
7z x pred_nets.z01
```  
  * Update file paths in the code
    > Before running the program, ensure that any file paths used in the code are correctly updated to match your own directory structure. This is important because the default paths in the code may not align with where you have stored the necessary files. To do this, locate the file paths in the Python scripts (e.g., in `main.py`) and modify them to reflect the actual locations of your files on your system.
    > For example, If the file path in the code is pd.read_csv('~/DeepTGI-main/DeepTGI/dataset/bulk_tf.csv'), change it to match your own directory structure.
```
pd.read_csv('~/DeepTGI/dataset/bulk_tf.csv')
```
  * Run the program
```
python main.py
```
* Choose the appropriate script based on the dataset
    > The main.py, main_hESC.py, and main_mHSC.py scripts are designed to work with different datasets. Make sure to use the correct script according to the dataset you want to analyze:
     * main.py is designed for the mESC dataset (mouse embryonic stem cells).
     * main_hESC.py is designed for the human dataset (human embryonic stem cells).
     * main_mHSC.py is designed for the mHSC-E and mHSC-L datasets (mouse hematopoietic stem cells in early and late stages).



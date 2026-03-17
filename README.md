# Composite Gene Signature Scoring Example
### Supporting code for the atherosclerosis macrophage study

This repository contains a Python notebook and supporting scripts demonstrating how to compute composite gene signature scores and reproduce example plots used in the manuscript.

The code provides a minimal reproducible example illustrating how a gene signature can be converted into a single activity score per sample, allowing comparison between biological states such as disease vs control.

---

# Repository contents

.
├── CompositeScore_example.ipynb   # Main notebook demonstrating the scoring workflow  
├── bone.py                        # Supporting functions for Boolean network explorer scoring  
├── RCT_LAM.txt                    # Example gene signature used in the study  
└── README.md  

---

# Overview

Gene signatures often contain multiple genes that collectively represent a biological pathway or cellular state. Instead of analyzing each gene individually, we compute a composite score that summarizes the activity of the entire signature in each sample.

The scoring approach follows the framework implemented in BoNE (Boolean Network Explorer) and used in the manuscript.

The workflow consists of three steps:

1. Binarization  
Gene expression is converted into high or low states using StepMiner thresholds.

2. Normalization  
Expression values are normalized relative to the threshold using a modified Z score.

3. Composite scoring  
The normalized expression values of all genes in the signature are summed to produce a composite score representing pathway activity in each sample.

This score reflects the overall activation state of the biological program represented by the signature.

---

# Example signature

The repository includes an example gene signature:

RCT_LAM.txt

This signature represents a macrophage program associated with reverse cholesterol transport (RCT) and lipid handling in atherosclerosis.

---

# What the notebook demonstrates

The notebook illustrates how to:

• Load expression data  
• Read a gene signature  
• Compute normalized gene values  
• Calculate composite scores  
• Visualize score distributions between groups  

Example visualizations include:

• violin plots  
• swarm plots  
• group comparisons  
• classification plots  

These plots illustrate how composite gene scores can stratify samples according to biological or disease states.

---

# Requirements

Python ≥ 3.8

Required packages:

pandas  
numpy  
matplotlib  
seaborn  
scikit-learn  

Install using:

pip install pandas numpy matplotlib seaborn scikit-learn

---

# Running the example

Clone the repository:

git clone https://github.com/sinha7290/Atherosclerosis.git
cd Atherosclerosis

Launch the notebook:

jupyter notebook CompositeScore_example.ipynb

Follow the cells sequentially to reproduce the scoring workflow and example plots.

---

# How to use with your own data

To compute scores on a new dataset:

1. Provide a gene expression matrix

genes x samples

2. Provide a gene signature file

one gene per line

3. Run the notebook with your dataset.

The pipeline will compute composite scores for each sample and generate visualization outputs.

---

# Notes

Composite scores are dataset dependent because normalization uses dataset specific thresholds. Therefore scores should only be compared within the same dataset and not across datasets.

The scoring framework can be applied to any biological pathway represented by a gene signature.

---

# Citation

If you use this code or approach, please cite the corresponding manuscript describing the composite gene scoring framework and macrophage lipid biology.

---

# License

MIT License

# AdaMBind

## Table of Contents

- [About](#about)
- [Getting Started](#getting_started)
- [Usage](#usage)

## About <a name="about"></a>

**AdaMBind: Drug-Target Affinity Prediction with Meta-Learning and Task Adaptation**

This project implements **AdaMBind**, a novel drug-target affinity (DTA) prediction model designed for cold-start and low-data scenarios, especially when dealing with newly identified or understudied protein targets. Built upon the MAML-based meta-learning framework, AdaMBind introduces a task-adaptive mechanism that dynamically evaluates task difficulty and importance, enabling robust generalization to unseen targets.

![Main Framework of AdaMBind](/figs/main.png)

## Getting Started <a name = "getting_started"></a>

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. 

### Prerequisites

To run this project, you need to install the following software and libraries:

- Python 3.8 or higher  
- PyTorch 2.3.1 or higher  
- RDKit (for molecular feature extraction)  
- Scikit-learn (for evaluation metrics)  
- NumPy and Pandas (for data processing)   
- torch_geometric (for GNN encoder)
- Networkx (for graph generation)

### Installing

We recommend using a virtual environment such as `conda` or `venv`. Here's an example using `conda`:


```
# Create a new conda environment
conda create -n adambind python=3.10
conda activate adambind
```


Install PyTorch with CUDA support
```
# CUDA 12.1
conda install pytorch==2.3.1 torchvision==0.18.1 torchaudio==2.3.1 pytorch-cuda=12.1 -c pytorch -c nvidia
```
Install other dependencies
```

pip install rdkit scikit-learn numpy pandas networkx torch_geometrics
```

## Usage <a name = "usage"></a>


This section provides step-by-step instructions on how to use the AdaMbind system for DTA prediction.

### Step 1: Prepare and Process the Dataset

Before training or evaluating the model, you need to preprocess the dataset. This includes parsing raw data, generating molecular graphs for drugs, and extracting features for protein targets.

To create the processed data files, run:

```bash
python create_data.py
```
- Note: Make sure your raw data is placed in `AdaMBind/data/raw`

### Step 2: Train or Evaluate the Model

Once the data is ready, you can proceed to train or evaluate the AdaMBind model using the provided shell script.

``` 
bash run.sh
```
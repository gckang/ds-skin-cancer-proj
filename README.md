# Detecting Skin Cancer
## Contents
### Goal Statement
The goal of this project is to fine tune an EfficientNet model to increase the accuracy of detecting skin cancer on low resolution images.
### Research Question
Can the EfficientNet model be fine tuned to detect skin cancer on images taken on smartphones?
## Section 1: Software and Platform
This project utilized Python, Jupyter Notebook, and GitHub. Both a Mac and Windows computer were used for this project, but this project can run on any platform that has the required installations. <br />
The packages needed for this project include pandas, pytorch, matplotlib.pyplot, numpy, sklearn.metrics, and seaborn 
The data was a file of 2,298 images with a patient ID as well as a csv file containing metadata about each patient. <br />
## Section 2: map of documentation
```bash
ds-skin-cancer-proj
├── DATA
│   ├── test.csv
│   ├── train.csv
│   ├── val.csv
│   ├── test2.csv
│   ├── train2.csv
│   ├── val2.csv
│   ├── metadata.csv
│   └── source data
├── OUTPUT
│   ├── finetune2_cm.png
│   ├── finetune_cm.png
│   ├── pretrain_cm.png
│   └──pretrain2_cm.png
├── SCRIPTS
│   ├──finetune.ipynb
│   ├──efficientnet_skin_cancer_classifier.pth
│   ├──best_model.pth
│   └── dataexploration-2.ipynb
├── LICENSE.md
└── README.md
```
## Section 3: instructions for reproducing results
### Acquiring the Data:
Because we were fine-tuning a model on our own image data, we had to set up a custom dataset to load into the model. 
First we downloaded the data from the website and saved it in a folder called ‘imgs_part_1’. From there, we split the data into train, test, and validation data by splitting it 60%, 20%, 20%. Because we ended up fine-tuning two separate models, we had a train, test, validation dataset for each model, meaning a total of six data files. For the first model where we classified six skin cancers and diseases, we created the datasets where it mapped each image file path to a corresponding numerical class that represented which skin cancer or disease it classified under. For the second model where we classified whether it was a skin cancer (malignant) or disease (benign), we created the datasets where it mapped each image file path to either 0 (benign) or 1 (malignant). We saved all of these datasets into the ‘data’ folder. <br /><br />
To actually load in the data, we created a new PyTorch library Dataset and set up the initialization to use a custom local file location for the data. We loaded in every dataset and applied transformations to each image, such as resizing to (244, 244) and normalization.<br /><br />
### Data Exploration:
The file “dataexploration-2.ipynb” was run. This created a data frame using the metadata csv file. This file created a graph of each type of diagnostic count, the distribution of male and female subjects, and counts of where each skin lesion was located. <br /><br />
### References:
[1] N. Klingler, “EfficientNet: Pushing the Boundaries of Deep Learning Efficiency,” viso.ai, Mar. 18, 2024. https://viso.ai/deep-learning/efficientnet/ <br /><br />
[2] A. Pacheco et al., “PAD-UFES-20: a skin lesion dataset composed of patient data and clinical images collected from smartphones,” data.mendeley.com, vol. 1, Jul. 2020, doi: https://doi.org/10.17632/zr7vgbcyr2.1.

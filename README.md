# DSA4213 Group26 Final Project
## Multimodal Fake News Detection
This project implements classifier models that incorporate multimodal features to perform fake news detection on the Fakeddit dataset.  

### Overview
Task: Fake News Classification

Dataset: [Fakeddit](https://github.com/entitize/Fakeddit)
* For this project, we used a subset of `multimodal_train.tsv`

Methods: 
* Random Forest
* BERT + ResNet
* CLIP

### GitHub Repository Navigation

Explanation of Directories and Files:

```
DSA4213-Group26/
├── scripts/
│ ├── preprocessing.ipynb       # EDA and preprocessing of fakeddit dataset
│ ├── RandomForest.ipynb        # baseline Random Forest classifier
│ ├── Bert_ResNet.ipynb         # fine-tuning of Bert and ResNet for multimodal model
│ └── CLIP.ipynb                # fine-tuning of CLIP for multimodal model
├── data/
│ ├── multimodal_train.tsv      # original dataset
│ ├── fakeddit_train.tsv        # train data
│ ├── fakeddit_val.tsv          # validation data
│ └── fakeddit_test.tsv         # test data
├── .gitignore                  # files excluded from version control
├── README.md                   # project information
└── requirements.txt            # Python dependencies
```

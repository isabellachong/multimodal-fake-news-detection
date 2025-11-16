# DSA4213 Group26 Final Project
## Multimodal Fake News Detection
Detecting misleading and fake news is a growing challenge as multimodal misinformation increasingly combines text and images, making it harder to discern real from misleading or fake claims. **This project evaluates unimodal BERT, ResNet50 models, a late-fusion BERT-ResNet model and several CLIP variants for three-class classification on a subset of the Fakeddit dataset.** 

Experimental results show that: 
* BERT outperforms ResNet50 across accuracy and F1-scores, reflecting the superior discriminative capabilities of text features for fake news detection.
* The BERT-ResNet fusion model achieved significantly higher accuracy and F1-scores than the unimodal models, suggesting that combining complementary textual and visual cues are beneficial in classifying ambiguous or borderline cases that single modalities struggle to identify.
* Fine-tuned CLIP models achieved the strongest overall results, benefiting from their ability to capture inter-modal relationships via joint alignment after task-specific adaptation.

These findings highlight the value of multimodal representation learning and demonstrate that models trained on cross-modal interactions offer the most effective approach for detecting multimodal misinformation.  

### Overview
Task: Ternary Fake News Classification
* Classifies sample as true, misleading or fake news

Dataset: [Fakeddit](https://github.com/entitize/Fakeddit)
* For this project, we used a subset of `multimodal_train.tsv`
* The train, validation and test splits we used can be found in the `data/` folder

Methods: 
* Unimodal
  * BERT (Text-only)
  * ResNet50 (Image-only)
* Multimodal
  * BERT-ResNet Late Fusion
  * CLIP
    * Zero-Shot Classification (Using handcrafted prompts and pretrained CLIP encoders)
    * Fine-Tune Classifier Head Only (Text and image encoders frozen; train only classifier)
    * Full Fine-Tuning (Optimisation of both encoders and classifier)

### GitHub Repository Navigation

Explanation of Directories and Files:

```
DSA4213-Group26/
├── scripts/
│ ├── preprocessing.ipynb       # EDA and preprocessing of fakeddit dataset
│ ├── Bert_ResNet.ipynb         # fine-tuning of Bert and ResNet for fusion model
│ └── CLIP.ipynb                # zero-shot and fine-tuned CLIP experiments
├── data/
│ ├── multimodal_train.tsv      # original dataset
│ ├── fakeddit_train.tsv        # train split
│ ├── fakeddit_val.tsv          # validation split
│ └── fakeddit_test.tsv         # test split
├── models/                     # folder to store saved models
├── .gitignore                  # files excluded from version control
├── README.md                   # project documentation
├── fusion_requirements.txt     # Python dependencies for BERT-ResNet fusion
└── requirements.txt            # Python dependencies for CLIP and preprocessing
```

### How to Run Experiments
1. Clone repository
```
git clone https://github.com/isabellachong/DSA4213-Group26
cd DSA4213-Group26
```
2. Install dependencies
   
For **BERT-ResNet fusion** experiments:
```
pip install -r fusion_requirements.txt
```
For **preprocessing and CLIP** experiments:
```
pip install -r requirements.txt
```
3. Open and execute the relevant notebooks to run experiments
```
scripts/preprocessing.ipynb       # data exploration and preprocessing
scripts/Bert_ResNet.ipynb         # BERT, ResNet50 and fusion fine-tuning
scripts/CLIP.ipynb                # CLIP zero-shot and fine-tuning
```

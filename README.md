# NLP Token Classification using BERT (POS Tagging & Chunking)

##  Project Overview

This project focuses on building a **Token Classification system** using **BERT (bert-base-uncased)** to perform:

- Part-of-Speech (POS) Tagging  
- Chunking (Phrase Detection - conceptual comparison)

The model assigns labels to each word in a sentence, enabling machines to understand grammar and sentence structure.

---

##  Objective

- Fine-tune a transformer model (BERT) for token classification  
- Perform POS tagging using sequence labeling  
- Understand and handle tokenization & label alignment  
- Demonstrate chunking concept through comparison  

---

##  Technologies Used

- Python  
- PyTorch  
- Hugging Face Transformers  
- Jupyter Notebook  

---

##  Dataset

- CoNLL-style formatted dataset  
- Contains:
  - Tokens (words)  
  - POS tags  

###  Label Categories (POS Tags)

Examples:
- NNP (Proper Noun)  
- VBZ (Verb)  
- JJ (Adjective)  
- IN (Preposition)  

---

##  Pipeline Flow
Raw Data → Preprocessing → Tokenization → Label Alignment → Model Training → Evaluation → Inference → Comparison

---

##  Implementation Steps

### 1. Data Loading & Extraction
- Extracted dataset from ZIP file  
- Loaded `train.txt` for processing  

### 2. Data Preprocessing
- Converted raw text into structured format  
- Created:
  - `sentences` (list of words)  
  - `labels` (POS tags)  

### 3. Label Mapping
- Converted labels into numerical format  
- Used:
  - `label2id`  
  - `id2label`  

### 4. Tokenization
- Used BERT tokenizer (`bert-base-uncased`)  
- Applied:
  - Padding  
  - Truncation  
  - Word-level tokenization  

### 5. Label Alignment
- Handled subword tokenization  
- Applied rules:
  - First token → label  
  - Subwords → -100  
  - Special tokens → -100  

### 6. Dataset Creation
- Created custom PyTorch dataset  
- Converted data into tensors  

### 7. Model Setup
- Used `AutoModelForTokenClassification`  
- Configured:
  - `num_labels`  
  - `id2label`, `label2id`  

### 8. Model Training
- Used Hugging Face `Trainer`  
- Configurations:
  - Learning rate: 2e-5  
  - Batch size: 16  
  - Epochs: 1  

### 9. Inference
- Tested model on custom sentence  

## Challenges Faced

- Handling subword tokenization  
- Aligning labels with tokens  
- Dataset formatting issues  
- Training time optimization  

---

##  Future Improvements

- Use larger dataset  
- Increase training epochs  
- Implement actual chunking prediction  
- Try DistilBERT for faster performance  

---

##  Conclusion

This project demonstrates how BERT can be fine-tuned for token classification tasks such as POS tagging. It highlights key NLP challenges like tokenization and label alignment while providing a complete end-to-end pipeline.

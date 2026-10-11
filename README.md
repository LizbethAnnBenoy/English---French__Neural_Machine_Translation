# English---French__Neural_Machine_Translation: Comparing Seq2Seq, Attention and Transformer models

## Overview
This project is to impliment nlp models of different levels from scratch and comparing them for English to french translation using pytorch.

1. **Seq2Seq**: GRU based Encoder Decoder model
2. **Seq2Seq with Attention**: GRU based Encoder decoder with with Bahdanau Attention
3. **Transformer**: Transformer Encoder Decoder model with Multihead attention.

## Aim
- Making three neural machine translation architectures from scratch
- Understanding limitaions of Vanilla Seq@Seq model
- How does Attention and Transformers improve translation
-  Comparing training and validation losses of the three models
-  Evluating qualtity if translations of each models using BLEU scores

## Dataset
https://www.kaggle.com/datasets/devicharith/language-translation-englishfrench

### Preprocessing 
- Removing rows with missing data
- Convert all text to lower case
- Seperating punctuation from words
- Tokenization of sentances using custom tokenizer
- Adding special tags or tokens for identification: `<PAD>`, `<UNK>`, `<SOS>`, and `<EOS>`.
- Making Embedding of tokens
- Padding embeddings to match the size

## Experimental Setup

| Parameter | Value |
|-----------|-------|
| Language Pair | English → French |
| Framework | PyTorch |
| Dataset Subset | 20,000 sentence pairs |
| Training Split | 80% |
| Validation Split | 20% |
| Batch Size | 32 |
| Training Epochs | 5 |
| Loss Function | Cross-Entropy Loss |
| Optimizer | Adam |

## Models
### 1. Vanilla Seq2Seq
A baseline model using GRU based Encoder decoder architecture

### 2. Seq2Seq with Bahdanau Attention
Extending Seq2Seq model with attention to inputs in input to decoder using weights
Help decoder at each timestep to focus on important parts on different places

### 3.  Transformer
Replacing PNN with attention based sequence modeling

**Encoder**
- Token embedding with positional embeddings
- Multi head attention

**Decoder**
- Maked attention and cross attention fromm encoder layes


## Experimental Results
### Validation Loss Comparison

| Model | Best Validation Loss | Epoch |
|-------|---------------------:|------:|
| Vanilla Seq2Seq | 4.559 | 5 |
| Seq2Seq + Bahdanau Attention | 3.730 | 4 |
| Transformer | **2.679** | 5 |

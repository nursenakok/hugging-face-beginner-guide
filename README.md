# Hugging Face Beginner Guide

A beginner-friendly guide to Hugging Face Transformers, with example notebooks for pipelines, tokenizers, attention mechanism.  
This repository contains personal experiments and notes on Hugging Face Transformers, created for self-learning purposes. It is not intended as formal educational material.

---

# PART I: Working with Pipelines 

### Available Pipelines

- Sentiment Analysis
- Named Entity Recognition (NER)
- Zero-Shot Classification
- Question Answering
- Text Generation
- Summarization
- Fill-Mask


# PART II: Tokenizer

### Overview

What is the primary function of a tokenizer in the contex of using a model like BERT?
    The primary function of a tokenizer in the context of models like BERT is to convert raw text into a format that the model can understand. Models don’t process plain text—they work with numbers. Tokenizers do     this by:
    
    1. Splitting text into tokens (words or subwords): Example: "I'm learning" → ['[CLS]','I', "'", 'm', 'learning','[SEP]']

    2. Mapping tokens to numerical IDs based on the model’s vocabulary: Example: ['[CLS]','I', "'", 'm', 'learning','[SEP]'] → [101,146, 112, 182, 3776,102]
 
    3. Creating additional inputs for the model, like:

          input_ids: the token IDs

          attention_mask: which tokens should be attended to

          token_type_ids: for sentence distinction (BERT-specific)

    4. Allowing conversion back to text (decoding), if needed


# PART III: Attention Mechanism 

### Required Libraries

!pip install transformers torch matplotlib seaborn

### What You'll Learn

- How self-attention works in transformer models
- Visualizing attention weights as heatmaps
- Comparing different attention heads and layers
- Understanding how BERT processes language


## Resources

- [Hugging Face Transformers Documentation](https://huggingface.co/docs/transformers/)
- [Hugging Face Course](https://huggingface.co/course/chapter1)
- [Transformers Library](https://github.com/huggingface/transformers)
- [Illustrated Transformer](http://jalammar.github.io/illustrated-transformer/)

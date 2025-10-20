# Hugging Face Beginner Guide

A beginner-friendly guide to Hugging Face Transformers, with example notebooks for pipelines, tokenizers, attention mechanism.  
This repository contains personal experiments and notes on Hugging Face Transformers, created for self-learning purposes. It is not intended as formal educational material.

---

## PART I: Working with Pipelines 

What You'll Learn: 
Use pre-trained models for common NLP tasks with minimal code. Pipelines simplify complex tasks like sentiment analysis or text generation.

### Available Pipelines 

- Sentiment Analysis: Predicts whether text expresses positive or negative sentiment.
- Named Entity Recognition (NER): Identifies entities like people, organizations, or locations in text.
- Zero-Shot Classification: Classifies text into custom categories without additional training.
- Question Answering: Extracts answers from a given context based on a question.
- Text Generation: Generates creative text continuations from a prompt.
- Summarization: Condenses long text into a concise summary.
- Fill-Mask: Predicts missing words in a sentence using a masked language model.

### Code Context:
Your pipeline code uses the transformers library for all tasks (Sentiment Analysis, NER, Zero-Shot Classification, Question Answering, Text Generation, Summarization, Fill-Mask).

### Required Libraries:

transformers: For loading and running Hugging Face pipelines.
No additional libraries are needed since the pipelines rely solely on transformers (and its dependencies like torch or tensorflow, which are automatically installed).

## PART II: Tokenizer

What You'll Learn: 
How tokenizers convert text into model-ready inputs (tokens → IDs → attention masks).

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

### Code Context:
Your tokenizer code uses AutoTokenizer from the transformers library to tokenize text and handle special tokens, attention masks, etc.

### Required Libraries:

transformers: For the AutoTokenizer class and tokenization functions.
No additional libraries are needed, as tokenization is handled entirely by transformers.

## PART III: Attention Mechanism 

What You'll Learn:
How self-attention works in transformers, visualized through heatmaps of attention weights.

![BERT - First Layer, First Head Attention Weights](https://raw.githubusercontent.com/nursenakok/hugging-face-beginner-guide/main/self-attention_heatmap.PNG)

### Contribution to the Attention Mechanism

This visual is an excellent tool for understanding how the attention mechanism works because:

- Highlights Relationships: It visualizes the relationships between tokens (e.g., the 0.21 weight between "sat" and "on"), showing how the model analyzes the structure of the sentence.
- Explains Weight Distribution: The distribution of attention weights reveals which words the model focuses on more (e.g., "mat" and "[CLS]") and which it overlooks (e.g., the low 0.03 weight between "the" and "the").
- Training and Error Analysis: Developers can use such maps to identify if the model’s attention is misplaced and improve the model accordingly.

### What You'll Learn

- How self-attention works in transformer models
- Visualizing attention weights as heatmaps
- Comparing different attention heads and layers
- Understanding how BERT processes language

### Code Context:
Your attention mechanism code uses transformers for the model and tokenizer, torch for model inference, and matplotlib and seaborn for visualizing attention weights as heatmaps. numpy is also used for handling attention weight arrays.

### Required Libraries:

transformers: For loading the model (AutoModel) and tokenizer.
torch: For running model inference and handling tensors.
matplotlib: For creating plots.
seaborn: For generating heatmaps.
numpy: For array operations on attention weights.

### Resources

- [Hugging Face Transformers Documentation](https://huggingface.co/docs/transformers/)
- [Hugging Face Course](https://huggingface.co/course/chapter1)
- [Transformers Library](https://github.com/huggingface/transformers)
- [Illustrated Transformer](http://jalammar.github.io/illustrated-transformer/)

# Introduction to Transformer

The **Transformer** is a deep learning model architecture introduced in the landmark paper *"Attention is All You Need"* by Vaswani et al. in 2017. It has since become the foundation for many state-of-the-art models in natural language processing (NLP), such as BERT, GPT, and T5.

## Key Features

- **Attention Mechanism**: Uses self-attention to capture relationships between all words in a sequence, regardless of their distance.
- **Parallelization**: Unlike RNNs, Transformers allow parallel processing of input data, significantly speeding up training.
- **Scalability**: Performs well on large datasets and can scale to billions of parameters.
- **No Recurrence**: Does not rely on sequential processing, avoiding the limitations of RNNs and LSTMs.

## Architecture Overview

The original Transformer architecture consists of an **encoder-decoder** structure:

### Encoder
- Input embeddings
- Positional encodings
- N repeated layers of:
  - Multi-head self-attention
  - Feed-forward neural network
  - Layer normalization and residual connections

### Decoder
- Output embeddings and positional encodings
- N repeated layers of:
  - Masked multi-head self-attention
  - Encoder-decoder attention
  - Feed-forward neural network
  - Layer normalization and residual connections

## Applications

Transformers have been used in a variety of tasks:
- **Machine Translation** (e.g., English to French)
- **Text Summarization**
- **Question Answering**
- **Text Generation**
- **Image Captioning** (with vision transformers)

## Popular Transformer-based Models

- **BERT** – Bidirectional Encoder Representations from Transformers
- **GPT** – Generative Pre-trained Transformer
- **T5** – Text-To-Text Transfer Transformer
- **ViT** – Vision Transformer (for image tasks)

## Further Reading

- [Attention Is All You Need (original paper)](https://arxiv.org/abs/1706.03762)
- [The Illustrated Transformer](https://jalammar.github.io/illustrated-transformer/)

---

> The Transformer has revolutionized deep learning by enabling powerful and flexible models across NLP, vision, and beyond.

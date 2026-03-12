# Arabic GPT from Scratch 

A GPT language model built entirely from scratch using PyTorch for Arabic poetry generation. No pretrained weights used.

## Demo
[Watch the full demo on YouTube](https://youtu.be/Hd7-H19IgsU)

##Dateset
**Pretraining:** Arabic Wikipedia XML dump — [download here](https://dumps.wikimedia.org/arwiki/)
**Fine-Tuning:** Ashaar Poetry Dataset — [HuggingFace](https://huggingface.co/datasets/arbml/ashaar)
  

## Model
- **Parameters:** 22,960,128 (~23M)
- **Architecture:** Decoder-Only Transformer (GPT-style)
- **Tokenizer:** ByteLevel BPE (16k vocab) trained on Arabic Wikipedia
- **Context Length:** 64 tokens

## Data
- **Pretraining:** Arabic Wikipedia — 50,000 clean lines, 6.7 MB
- **Fine-Tuning:** Ashaar dataset (HuggingFace) — 500 Arabic poetry pairs

## Training Results
- Pretraining loss: 2.28 → 0.59 (73.8% improvement)
- Fine-tuning loss: 4.93 → 1.60
- Perplexity: 65,697 → 1.45 after fine-tuning

## Evaluation
- **LLM Judge (Ollama gemma3:4b):** Average 1.7/5
- **Failure modes:** Incoherent grammar, context loss, no rhyme scheme
- **Cause:** Small model size (23M vs 117M for GPT-2)

## Files
- `MyGPT.ipynb` — Full training notebook (Google Colab)
- `README_Arabic_GPT.docx` — Full project documentation

## Future Work
- Scale to 117M+ parameters
- Increase context to 512+ tokens
- Train on 100,000+ poems

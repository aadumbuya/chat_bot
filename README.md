# chat_bot
## English Grammar Chatbot

This project is a Grammar Chatbot trained using the CoLA dataset (Corpus of Linguistic Acceptability). The chatbot is built with BERT for sequence classification, trained to assess grammatical acceptability, and can be interacted with via a command-line interface.

## Table of Contents
- Installation
- Training the Model
- Saving and Loading the Model
- Interacting with the Model
- Project Structure
- Acknowledgments

## Installation

Make sure you have Python 3.8+ installed. Then, install the required dependencies:

```bash
pip install torch transformers tqdm numpy
```

## Training the Model

The training script is provided as a Jupyter Notebook (English_Grammar_Chatbot.ipynb). To train the model, open the notebook and run all cells.

### Training Process:
- The model is trained using the CoLA dataset.
- It uses BERT for Sequence Classification.
- Tracks training loss and training accuracy per epoch.
- The trained model is saved for later use.

## Saving and Loading the Model

The model is saved after training to ensure it can be loaded for future inference:

Saving the model:
```python
model.save_pretrained(output_dir)
tokenizer.save_pretrained(output_dir)
```

Loading the model for inference:
```python
loaded_model, loaded_tokenizer = load_model(output_dir)
```

## Interacting with the Model

A command-line interface (CLI) script (interact.py) is provided to interact with the trained chatbot.

To start the chatbot, run:

```bash
python interact.py
```

### Example Usage:
```
You: This sentence is correct.
Bot: Acceptable

You: He to go the store.
Bot: Unacceptable
```

## Project Structure
```
 English_Grammar_Chatbot.ipynb                   # Jupyter Notebook for training the model
 interact.py                                     # Command-line interface for chatbot interaction
 bert_finetuned_model                            # Folder for trained model weights
 in_domain_train.tsv, out_of_domain_dev.tsv      # Training and evaluation datasets
 README.md                                       # Project documentation
```


## Acknowledgments
- Hugging Face Transformers
- PyTorch
- CoLA Dataset

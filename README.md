
# Character-Level Language Model - Shakespeare Text Generator

This project implements a character-level language model using PyTorch, trained on the complete works of Shakespeare. The model uses a transformer-based architecture, drawn from GPT-2, to learn Shakespeare's writing style and generate similar text.

## Features
- **Character Encoding and Decoding**: Maps each character in the text to a unique integer.
- **Transformer Architecture**: Uses multiple transformer layers to learn sequential character patterns.
- **Configurable Hyperparameters**: Includes customizable settings for batch size, block size, learning rate, and more.
  
## Dependencies

1. PyTorch
2. NumPy

3. DATA: Prepare the Shakespeare text data (or any desired training text) as `input.txt` in the same directory as the script.

## Hyperparameters

Key hyperparameters that can be adjusted in the script:
- **`batch_size`**: Number of sequences processed in parallel.
- **`block_size`**: Maximum context length for predictions.
- **`learning_rate`**: Controls the model's training speed.
- **`n_embd`, `n_head`, `n_layer`**: Configure the embedding size, number of attention heads, and transformer layers.

## Usage

To train the model on Shakespeare's text, run:

```bash
python gpt-llm.py
```

Ensure `input.txt` is in the same directory, containing the text data for training. During training, the model will periodically evaluate itself to track performance. The model will then output a segement of text generated from the trained model.

## Workflows

1. **Data Preparation**:
   - Reads `input.txt` and builds mappings for character-to-integer encoding and decoding.
   - Encodes the text for input to the model.

2. **Model Training**:
   - The transformer model is trained to predict the next character given a sequence of preceding characters.
   - Progress can be tracked based on evaluations at intervals defined by `eval_interval`.

3. **Text Generation**:
   - After training, the model can generate text in a style similar to Shakespeare's by sampling from the learned character sequences.

## Output

After sufficient training, the model generates Shakespearean-style text. The hyperparameters can be experimented with to optimize model accuracy. In its current state, the model is not very optimized, and the outputted text is mostly gibberish. This project is mostly a proof of concept to manually reproduce the transformer architecture used in GPT-2.


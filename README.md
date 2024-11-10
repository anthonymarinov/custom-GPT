
# Character-Level Language Model - Shakespeare Text Generator

This project implements a character-level language model using PyTorch, trained on the complete works of Shakespeare. The model uses a transformer-based architecture to learn the nuances of Shakespeare's writing style and generate similar text.

## Features
- **Character Encoding and Decoding**: Maps each character in the text to a unique integer, allowing the model to handle text data effectively.
- **Transformer Architecture**: Uses multiple transformer layers to learn sequential character patterns.
- **Configurable Hyperparameters**: Includes customizable settings for batch size, block size, learning rate, and more.
  
## Installation

1. Clone the repository or download the `gpt-llm.py` file.
2. Install the required dependencies:
   ```bash
   pip install torch numpy
   ```

3. Prepare the Shakespeare text data as `input.txt` in the same directory as the script. You can use any other text corpus as well.

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

Ensure `input.txt` is in the same directory, containing the text data for training. During training, the model will periodically evaluate itself to track performance.

## Workflows

1. **Data Preparation**:
   - Reads `input.txt` and builds mappings for character-to-integer encoding and decoding.
   - Encodes the text for input to the model.

2. **Model Training**:
   - The transformer model is trained to predict the next character given a sequence of preceding characters.
   - Progress can be tracked based on evaluations at intervals defined by `eval_interval`.

3. **Text Generation**:
   - After training, the model can generate text in a style similar to Shakespeare's by sampling from the learned character sequences.

## Example Output

After sufficient training, the model generates Shakespearean-style text. Adjust the number of training iterations (`max_iters`) to refine the generated output quality.

## License

This project is open-source under the MIT License.

# Translator


# French to Wolof Translation using MarianMT

This project demonstrates how to fine-tune a MarianMT model for translating French text into Wolof using Hugging Face's `transformers` library.
The code is designed to preprocess data, train the model, and evaluate its performance on a given dataset.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Dataset](#dataset)
- [Usage](#usage)
- [Training the Model](#training-the-model)
- [Evaluating the Model](#evaluating-the-model)
- [Translating Text](#translating-text)
- [Contributing](#contributing)
- [License](#license)

## Prerequisites

Before running the code, ensure you have the following installed:
- Python 3.6 or later
- pip (Python package manager)

## Installation

You can install the required libraries using pip. It is recommended to create a virtual environment for this project:

```
# Create a virtual environment (optional)
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`

# Install the required packages
pip install pandas transformers evaluate
```

## Dataset

The code requires two CSV files:
1. `train.csv`: This should contain two columns: `FRENCH` and `WOLOF`, where `FRENCH` is the input text and `WOLOF` is the corresponding translated text.
2. `test.csv`: This should contain only the `FRENCH` column, which will be used to evaluate the model's performance.

**Example of `train.csv` structure:**

| FRENCH               | WOLOF                |
|----------------------|----------------------|
| Bonjour              | Nanga def            |
| Comment ça va ?      | Naka nga def ?       |

**Example of `test.csv` structure:**

| FRENCH               |
|----------------------|
| Bonne continuation.   |

## Usage

After setting up the environment and preparing the dataset, you can run the training and evaluation process. The main code handles loading the data, preprocessing, training the model, and translating new sentences.

### Training the Model

To train the model, simply run the main script:

```bash
python train_translate.py
```

### Evaluating the Model

The model will automatically evaluate its performance on the test dataset after training. You can customize the evaluation metrics in the `Trainer` class as needed.

### Translating Text

To translate new French sentences, modify the `translate_text` function or call it directly within the script:

```python
french_text = "Bonne continuation."
wolof_translation = translate_text(french_text)
print(f"Wolof Translation: {wolof_translation}")
```

## Contributing

If you want to contribute to this project, feel free to fork the repository and submit a pull request. Any improvements, bug fixes, or additional features are welcome!

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.


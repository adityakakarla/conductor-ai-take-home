# Air Force Data Numerical Value Extraction

This project extracts the highest numerical value from a PDF document, utilizing various approaches to ensure accuracy and flexibility. It employs techniques such as regular expressions, scale detection, and a language model (Llama 3.2) for parsing numerical data.

## Requirements

- Python 3.x
- PyPDF2
- Ollama

Make sure to install the necessary packages. You can use `pip` to install them:

```bash
pip install PyPDF2 ollama
```

## Installation

Clone the repository to your local machine:

```bash
git clone https://github.com/adityakakarla/conductor-ai-take-home
```

## Usage

To use the code, you need to specify the PDF file path. The function `find_largest_number` is the main entry point to extract the largest numerical value. You can also choose whether to consider scale factors (e.g., million, billion).

### Example

```python
largest_number = find_largest_number('your_file.pdf', scale=True)
print(f"Largest Number: {largest_number}")
```

## Approaches

### Approach 1: Using RegEx to Find Highest Numerical Value (No Scale)

This approach uses regular expressions to identify numerical values in the text extracted from the PDF. It returns the highest value found, without considering any scale context.

```python
largest_number = find_largest_number('air_force_data.pdf')
```

### Approach 2: Finding Highest Numerical Value Including Scale Factor

This method improves upon the first by accounting for scale (e.g., converting "$1 million" to its numerical equivalent). However, it may still miss some numbers.

```python
largest_number = find_largest_number('air_force_data.pdf', scale=True)
```

### Approach 3: Using Llama 3.2 to Parse Numerical Data

This approach leverages the Llama 3.2 model to extract numerical values. While it may provide more context by understanding variations in text (like "$1000000" or "$1 million"), it is the least reliable and slower due to its reliance on an AI model.

To run this, you will need to install Ollama and use the Llama 3.2 1B model. Other models can also be used, but you may experience significantly slower response times.

```python
largest = find_largest_number_using_llama('air_force_data.pdf')
```

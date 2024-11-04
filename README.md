# PREDICTIVE-TEXT-INPUT
## Overview

The Predictive Text Input project utilizes a pre-trained language model to generate predictions for the next word(s) based on user input. This project demonstrates the application of Natural Language Processing (NLP) techniques using Python and the `transformers` library.

## Features

- Generates predictions for the next word(s) based on input phrases.
- Uses the GPT-2 language model for text generation.
- Supports multiple predictions for each input.
- Easy to extend and modify for various use cases.

## Requirements

To run this project, you will need:

- Python 3.x
- Libraries:
  - `transformers`
  - `torch`

You can install the required libraries using pip:

```bash
   pip install transformers torch
Usage
   Clone the repository:
      git clone <repository-url>
      cd predictive-text-input
      Open the project in Google Colab or your local environment.

Run the following code to load the model and generate predictions:

python

from transformers import pipeline

def predict_next_word(input_text):
    # Load the text generation pipeline
    generator = pipeline('text-generation', model='gpt2')

    # Generate predictions based on the input text
    predictions = generator(input_text, max_length=len(input_text.split()) + 5, num_return_sequences=3)

    # Print the predicted text
    for prediction in predictions:
        print(prediction['generated_text'])

# Example inputs
inputs = [
    "The weather today is",
    "I am planning to go",
    "Artificial Intelligence is",
    "The future of technology involves"
]

for input_text in inputs:
    print(f"Input: {input_text}")
    print("Predictions:")
    predict_next_word(input_text)
    print()
Modify the inputs list to test different phrases.

Example Output

Input: The weather today is
Predictions:
The weather today is going to be sunny and warm all week.
The weather today is unusually cold for this time of year.

Input: I am planning to go
Predictions:
I am planning to go to the beach this weekend with my friends.
I am planning to go for a long hike in the mountains tomorrow.
License
This project is licensed under the MIT License. See the LICENSE file for more details.

Acknowledgments
Hugging Face for the transformers library.
OpenAI for the GPT-2 model.

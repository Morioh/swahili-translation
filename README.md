## Simple English-Swahili Translation Model

### Introduction

This project aims to build a simple translation model using a very small dataset of around 10 sentences. The objective is to translate short sentences from English to another language. Given the dataset's limited size, the project focuses on understanding the model's performance, identifying its limitations, and exploring areas for improvement.

---

### Dataset Creation and Preprocessing

- **Dataset**:
  - The dataset contains 10 manually gathered sentence pairs for English-to-target language translation.
  - Example:
    - **English**: "I have a headache."
    - **Translation**: "Kichwa kinauma."

- **Preprocessing Steps**:
  1. **Tokenization**: Sentences were split into individual words.
  2. **Padding**: Applied to ensure all inputs have equal length.
  3. **Vocabulary**: A limited vocabulary was created for both source and target languages.
  4. **Encoding**: Each word was mapped to an integer for neural network processing.

---

### Model Architecture and Design Choices

- **Model Architecture**:
  - **Encoder**:
    - Converts input sentences into hidden state representations using LSTM layers.
  - **Decoder**:
    - Generates translated sentences using the encoder's hidden state and LSTM layers.
  - **Embedding Layer**:
    - Represents words as dense vectors for both the encoder and decoder.
  - **Attention Mechanism** (Optional):
    - Not implemented in this iteration but could improve accuracy by focusing on relevant parts of input sentences.

---

### Training Process and Hyperparameters

- **Training Details**:
  - The model was trained for a few epochs with a small learning rate to prevent overfitting.

- **Hyperparameters**:
  - **Optimizer**: Adam optimizer with a learning rate of 0.001.
  - **Batch Size**: 1 (due to the small dataset).
  - **Epochs**: 100.
  - **Loss Function**: Categorical cross-entropy.
  - **Dropout**: Used in encoder and decoder to prevent overfitting.

---

### Evaluation Metrics and Results

- **Metrics**:
  - **Accuracy**:
    - Accuracy:75.2747%
    - Loss: 1.3987
    - High accuracy on the training set, likely due to overfitting given the small dataset.
  - **BLEU Score**:
    - The model performed poorly on BLEU, with scores close to zero, indicating poor translation quality.

- **Sample Outputs**:
  - **Sentence 1**:
    - **English**: "Can you keep a secret?"
    - **Predicted**: "token je una"
    - **Reference**: "Je, unaweza kutunza siri?"
    - **BLEU Score**: 0
  - **Sentence 2**:
    - **English**: "It would have been better if you had not gone there."
    - **Predicted**: "token bora kwenda shule"
    - **Reference**: "Bora usingekwenda hapo."
    - **BLEU Score**: 0

---

### Conclusion

Despite achieving high training accuracy, the model struggles to produce valid translations due to the extremely small dataset. The poor BLEU scores highlight the limitations of training on such a limited dataset. Future improvements include using a larger and more diverse dataset, adding an attention mechanism, and further fine-tuning the model to improve translation quality.

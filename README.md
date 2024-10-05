

# Text Translation (Fine-Tuning mT5 for English-to-Tamil Translation)

This project demonstrates **machine translation** with **fine-tuning** of a pre-trained `mT5` (multilingual T5) model. The fine-tuning process updates the model's weights to adapt it specifically for translating **English** sentences into **Tamil**, improving performance on this specific task while leveraging the model's pre-existing knowledge from multilingual training.

### Process Overview

1. **Data Input**:
   - A text file containing English sentences and their corresponding Tamil translations is used as input.
   - The data is preprocessed by tokenizing the sentences to prepare them for model training.

2. **Training the Model**:
   - The `train_model` function fine-tunes the mT5 model using the preprocessed English and Tamil sentence pairs.
   - **Teacher forcing** is applied during training, where the model is given the correct Tamil output to speed up learning.
   - **Batch training** is used for efficiency, with the data shuffled before each epoch to ensure randomness.
   - The model's weights are updated using the **AdamW** optimizer, and the learning rate is adjusted dynamically based on performance using a **learning rate scheduler** (`ReduceLROnPlateau`).

3. **Saving the Model**:
   - After training, the model is saved in a contiguous format to avoid potential issues with model parameter saving using the `save_model_contiguously` function.


Here the BLEU score evaluates to 0 as predicted translation has no overlapping 3-grams with the reference sentence (i.e., the hypothesis contains 0 counts of 3-gram overlaps).




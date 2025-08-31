# Pokemon_classification

Pipeline used:

**Data Loading & Exploration:** Loaded Pokémon data from 'pokemon.csv', checked for nulls, inspected unique 'Type1' values, and visualized their distribution using Seaborn.

**Image Extraction**: Unzipped a folder of Pokémon images and mapped each Pokémon name to its corresponding .png image file.

**Train/Val/Test Split**: Split the dataset (names and types) into training, validation, and test sets using train_test_split.

**Image Path Preparation**: Created lists of file paths corresponding to images for each split (train/val/test), checked file existence, and matched labels.

**Image Visualization**: Used Pillow and Matplotlib to visualize a few sample images alongside their associated 'Type1' labels.

**Type Encoding**: Used MultiLabelBinarizer to encode the 'Type1' labels as one-hot vectors for model training.

**Image Preprocessing**: Defined a TensorFlow image preprocessing pipeline (resize to 128x128, normalize) and created batched tf.data.Dataset objects for train, val, and test sets.

**Model Construction**: Built a sequential CNN with three convolution/pooling layers, a dense and dropout layer and a final softmax classification layer with categorical cross-entropy loss.

**Training & Evaluation**: Trained the model for 20 epochs, plotted accuracy/loss curves, and evaluated on the test set, resulting in ~22% test accuracy.

**Prediction Example**: Displayed a sample predicted label from the test set.

Furhter Improvements:

**Model Architecture**: Switched to a transfer learning approach, freezing a pre-trained MobileNetV2 backbone and stacking custom dense layers for classification.

**Regularization & Augmentation**: Integrated data augmentation (random flips, zooms, rotations) and dropout to combat overfitting.

**Training & Evaluation**: Monitored training/validation loss and accuracy for 13 epochs with early stopping. Best test accuracy achieved was 0.27 (27%).

**Performance Visualization**: Plotted training vs. validation loss and accuracy, providing insight into learning dynamics and model generalization. We can clearly see the improvement in test accuracy from 22% to 27%

# Plant Classification Challenge

## Description
the task was to classify a dataset containing images of healthy and unhealthy plants. The images are in RGB format with a resolution of 96 x 96 pixels. The project involves various techniques such as dataset cleaning, augmentation, and model experimentation to achieve high classification accuracy.

## Problem Statement
The challenge was to accurately classify plant images as either healthy or unhealthy. Initial experiments revealed outliers in the dataset, which necessitated a cleaning process to ensure high-quality data for training and evaluation.

## First Experiments
- **Dataset Splitting:** Used `train_test_split` from `sklearn.model_selection` to divide the dataset into 70% training, 20% evaluation, and 10% testing sets.
- **Sequential Models:** Created a LeNet model with Keras, achieving 0.77 validation accuracy and 0.67 test accuracy. Further experiments with MobileNetV2 improved hidden test set accuracy to around 0.72.

## Keras Applications
- **EfficientNet:** Experimented with EfficientNetB7, EfficientNetV2S, and EfficientNetV2M models. The EfficientNetV2M network achieved the best results with 0.8 accuracy on the hidden test set.
- **ConvNeXt:** Tested ConvNeXtTiny, ConvNeXtSmall, ConvNeXtBase, and ConvNeXtLarge models. ConvNeXtBase performed best, achieving 0.92 accuracy on the hidden test set.

## Dataset Cleaning
- Removed outliers and duplicate images to avoid overfitting.

## Augmentation Techniques
- **Undersampling:** Reduced the number of healthy plant images to match unhealthy ones, but it worsened classification accuracy.
- **Class-Weights:** Applied higher training weights to under-represented unhealthy plants, resulting in minimal improvement.
- **Oversampling:** Duplicated unhealthy plant samples and applied augmentation techniques using `keras_cv` library, creating a balanced dataset of 12,240 samples.

## Preprocessing
- Applied various preprocessing layers such as RandomContrast, RandomBrightness, RandomFlip, RandomRotation, RandomCrop, and final resizing to (96, 96) pixels.

## Avoiding Overfitting
- Utilized EarlyStopping callback to monitor validation accuracy.
- Applied dropout (0.5 rate) and ridge regression techniques to reduce overfitting.

## Final Submission
- Achieved 0.839 accuracy on the hidden test set using ConvNeXtBase model after augmenting the dataset and applying simpler preprocessing techniques.

## Improvements
- Considered ensemble learning by combining three models trained on different augmented datasets to improve performance.

## Results
| Model           | Accuracy |
|-----------------|----------|
| LeNet           | 0.77     |
| MobileNetV2     | 0.72     |
| EfficientNetV2M | 0.80     |
| ConvNeXtBase    | 0.92     |
| ConvNeXtLarge   | 0.871    |
| Final Model     | 0.839    |

## Contributions

## References
- Notebooks: 
  - “Chall1 DataCleanUp.ipynb”
  - “Chall1 Duplicates.ipynb”
  - “Chall1 LeNetModel.ipynb”
  - “Chall1 EffNetV2MDropout 0.85.ipynb”
  - “Chall1 ConvNextBase 0.92.ipynb”
  - “Chall1 RandAugmentDatasetConvL 0.871.ipynb”
  - “Chall1 Ensamble.ipynb”


## Acknowledgments
- **Francesco Ferrari:** 
- **Luca Bresciani:** 
- **Francesco Pastori:** 
- **Roberto Cialini:** 



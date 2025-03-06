# Lex_AI_AppliedAI_COMP6721
# COMP6721 Applied AI - Indoor/Outdoor Museum Classification Project

This project implements and compares different machine learning approaches for classifying museum images as indoor or outdoor.

## Contributors
| Group     | Student Name   | Student ID |
|-----------|---------------|------------|
| Lex AI    | Navachethan Murugeppa    | 40306253   |
|           | Aditya Sawant    | 40311540   |
|           | Priyanka Vaghela  | 40267831   |

## Dataset

The dataset consists of museum images from the Places365 dataset, organized into two classes:

- **museum-indoor**: Indoor museum environments showing exhibits, galleries, and interior spaces
- **museum-outdoor**: Exterior views of museum buildings and surrounding areas

Each class contains approximately 5,000 images, for a total of 10,000 images. All images were processed in both RGB and grayscale formats and resized to 128×128 pixels in some cases. The dataset was split into training (80%) and testing (20%) sets with stratified sampling to maintain class distribution.

## Project Overview

This project explores multiple approaches to image classification:

1. **Supervised Decision Tree (RGB and Grayscale)**
   - Using full 3-channel color and single-channel grayscale information
   - With and without feature scaling

2. **Semi-Supervised Learning with Decision Trees**
   - RGB implementation 
   - Grayscale implementation 

3. **Feature Engineering Approaches**
   - Raw pixel values
   - MinMaxScaler normalization
   - Color histograms

## Methodology

### Data Preprocessing
- Images were resized to 128×128 pixels
- RGB and grayscale conversion pipelines
- Features flattened to 1D vectors for decision tree processing
- Feature scaling applied in selected experiments

### Supervised Learning Implementations
Decision tree classifiers were trained with various configurations:
- Criterion: Entropy and Gini impurity
- Max depth: Range of values tested (6-12)
- Min samples split: Range of values tested (2-10)
- Random state: 42 for reproducibility

### Semi-Supervised Learning
The semi-supervised approach follows this algorithm:
1. Start with a small subset of labeled data (20% of training data)
2. Train an initial model on the labeled data
3. Use the model to predict labels for unlabeled data
4. Add high-confidence predictions (≥0.85) to the labeled pool
5. Retrain the model and repeat the process
6. Stop when no more high-confidence predictions are available or quality thresholds are not met


## How to run the notebooks
1. Clone the Repository
```bash
git clone https://github.com/Navachethan-Murugeppa/Lex_AI_AppliedAI_COMP6721.git
```
2. Make sure the latest python (3.9) is installed
3. Launch jupyter notebook in anaconda prompt
```bash
jupyter notebook
```
4. Run the notebooks individually.

Note:
- Run the training models first. If the data is not normalized, run the AI_normalize_data.ipynb first.
- Run the training notebooks first with the names AI_modelsRGB.ipynb, AI_modelsRGBminmax.ipynb and AI_modelsgrey.ipynb.
- Note that the necessary libraries are imported initially in the first cell.
- Later run the AI_testmodles.ipynb to test the trained models on the test data.
- For ease the nexessary trained models over the data is also available in the pickle format (.pkl).




## References
- http://places.csail.mit.edu/downloadData.html
- B. Zhou, A. Lapedriza, J. Xiao, A. Torralba, and A. Oliva. “Learning Deep Features for Scene Recognition using Places Database.” Advances in Neural Information Processing Systems 27 (NIPS), 2014


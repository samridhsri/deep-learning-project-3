# Adversarial Attacks on Deep Neural Networks

This project explores various adversarial attack methods on deep neural networks, focusing on the ResNet-34 architecture and its robustness against different types of attacks.

## Team
- Samridh Srivastava (ss18906)
- Krittin Nagar (kn2670)
- Shikhar Malik (sm12762)

## Project Overview

The project consists of five main tasks that progressively explore different aspects of adversarial attacks:

1. **Basics**: Evaluation of pretrained ResNet-34 on ImageNet-1K
2. **Pixel-wise Attacks**: Implementation of FGSM (Fast Gradient Sign Method)
3. **Improved Attacks**: Enhanced attack methods under ε constraints
4. **Patch Attacks**: Localized adversarial attacks
5. **Transferring Attacks**: Cross-model attack transferability analysis

## Tasks

### Task 1: Basics
- Load pretrained ResNet-34 model on ImageNet-1K
- Evaluate on provided test dataset (100 ImageNet classes)
- Report top-1 and top-5 accuracy
- Use provided preprocessing (mean/std)
- Match predictions using provided .json for class indices

### Task 2: Pixel-wise Attacks (FGSM)
- Implement FGSM with ε = 0.02
- Perturb all pixels within budget
- Save as "Adversarial Test Set 1"
- Visualize 3-5 classification failure examples
- Verify visual similarity and L∞ distance ≤ 0.02
- Report accuracies (target: ≥50% drop from Task 1)

### Task 3: Improved Attacks
- Implement enhanced attack methods under same ε constraint
- Save as "Adversarial Test Set 2"
- Visualize 3-5 failure examples
- Verify visual similarity and L∞ ≤ 0.02
- Report accuracies (target: ≥70% drop from Task 1)

### Task 4: Patch Attacks
- Apply best attack method to 32x32 patch only
- Allow ε up to 0.3-0.5
- Save as "Adversarial Test Set 3"
- Visualize 3-5 examples
- Report accuracy metrics

### Task 5: Transferring Attacks
- Evaluate all datasets on DenseNet-121
- Compare top-1/top-5 accuracy across all sets
- Analyze transferability and trends
- Propose mitigation strategies

## Deliverables

1. **4-page Report**
   - AAAI 2024 format
   - PDF submission for Gradescope

2. **GitHub Codebase**
   - Reproducible code
   - Plots and visualizations
   - Accuracy metrics
   - Clear documentation

## Requirements

- PyTorch
- torchvision
- numpy
- matplotlib
- PIL
- json

## Results

- **Task 1**
  - Top-1 Accuracy: 76.00% (380/500)
  - Top-5 Accuracy: 94.00% (470/500)

- **Task 2**
  - Adversarial Evaluation Result (Fast Gradient Sign Method (FGSM))
    - Top-1 Accuracy: 13.60%
    - Top-5 Accuracy: 34.40%

- **Task 3**
  - Adversarial Evaluation Results (Multiple gradient steps (Using PGD here))
    - Top-1 Accuracy: 1.00%
    - Top-5 Accuracy: 10.20%

- **Task 4**
  - Adversarial Evaluation Results (Patch Attack)
    - Patch Attack Top-1 Accuracy: 11.20%
    - Patch Attack Top-5 Accuracy: 32.00%

- **Task 5**
  - Using DenseNet121
    - Evaluating Original dataset on DenseNet-121:
      - Top-1: 74.60%
      - Top-5: 93.60%
    - Evaluating FGSM dataset on DenseNet-121:
      - Top-1: 35.80%
      - Top-5: 59.60%
    - Evaluating PGD dataset on DenseNet-121:
      - Top-1: 39.00%
      - Top-5: 64.40%
    - Evaluating Patch dataset on DenseNet-121:
      - Top-1: 41.80%
      - Top-5: 65.60%
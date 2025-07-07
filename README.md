# ♻️ Edge AI Waste Classification System
A lightweight TensorFlow Lite model that classifies waste materials as **Organic** or **Recyclable**, optimized for edge devices like Raspberry Pi.

## Performance Summary
| Metric              | Score  | Best Epoch |
|---------------------|--------|------------|
| **Validation Accuracy** | 86.97% | Epoch 4    |
| **Model Size**       | 1.2MB  |            |
| **Inference Speed**  | 58ms   | (RPi 4)    |

## Key Features
- Real-time classification on edge devices
- Optimized for low-power environments
- Simple integration with existing systems

## Training Progress
![download (1)](https://github.com/user-attachments/assets/3402a92f-bf37-462c-8286-9d0c39996fda)

**Key Observations:**
- Peak validation accuracy reached by Epoch 4
- Clear overfitting pattern emerges after Epoch 6
- Best balanced performance at Epoch 4

## Model Architecture
![download (1)](https://github.com/user-attachments/assets/9e4e62ed-a65e-46fb-b277-c2672cb0d9b3)

graph LR
    A[Input Image<br>180×180×3] --> B[Conv2D-16]
    B --> C[MaxPooling]
    C --> D[Conv2D-32]
    D --> E[MaxPooling]
    E --> F[Conv2D-64]
    F --> G[MaxPooling]
    G --> H[Flatten]
    H --> I[Dense-128]
    I --> J[Output Layer<br>2 Classes]
# Dataset Composition
![download](https://github.com/user-attachments/assets/f5e5ac47-49b1-4290-834b-7595cdac6aa3)
# Class	Samples	Description
Organic	7,532	Food waste, leaves
Recyclable	6,894	Plastics, glass, metal
## Deployment Guide
Requirements:

    Raspberry Pi 3/4
    
    Camera module
    
    TensorFlow Lite runtime

# Setup:

   # bash
    1. sudo apt-get install python3-pip
    2. pip3 install tflite-runtime
    3. Run Inference:
 # bash
    1. python3 classify.py --model waste_classifier.tflite
## Suggested Improvements
# Data Augmentation
    1. Random rotations (±20°)
    2. Horizontal flips
    3. Brightness adjustments
# Model Optimization
    1. Quantization to INT8
    2. Pruning to reduce size
    3. Knowledge distillation

# License
MIT License - Free for academic and commercial use

# ♻️ Edge AI Waste Classification System

![Project Banner](https://i.imgur.com/EDFkR3P.png)

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
![Training Metrics](https://i.imgur.com/JQ8W0vA.png)

**Key Observations:**
- Peak validation accuracy reached by Epoch 4
- Clear overfitting pattern emerges after Epoch 6
- Best balanced performance at Epoch 4

## Model Architecture
```mermaid
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
https://i.imgur.com/5Xc3k9L.png

# Class	Samples	Description
Organic	7,532	Food waste, leaves
Recyclable	6,894	Plastics, glass, metal
🚀 Deployment Guide
Requirements:

    Raspberry Pi 3/4
    
    Camera module
    
    TensorFlow Lite runtime

Setup:

bash
sudo apt-get install python3-pip
pip3 install tflite-runtime
Run Inference:

bash
python3 classify.py --model waste_classifier.tflite
🛠️ Suggested Improvements
Data Augmentation

Random rotations (±20°)

Horizontal flips

Brightness adjustments

Model Optimization

Quantization to INT8

Pruning to reduce size

Knowledge distillation

# License
MIT License - Free for academic and commercial use

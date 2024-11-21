# Faster-R-CNN-ResNet50-v2

Objective

The goal was to fine-tune a pre-trained Faster R-CNN ResNet50 v2 model for object detection on the COCO-Stuff dataset, which includes 183 object classes. The focus was on optimizing detection accuracy for natural elements like trees, mountains, rivers, and seas etc.

Approach

 Model & Pre-Trained Weights: 

Used Faster R-CNN ResNet50 v2 with ImageNet1k weights for transfer learning.

 Training Strategy:

 Warmup Training: 

10 epochs with StepLR (LR = 1e−3, decreased every 3 steps).

 Fine-Tuning: 

20 epochs with ReduceLROnPlateau (factor = 0.1, patience = 4).

 Optimizer:
 Differential learning rates:
 Backbone: 1e−5, RPN: 1e−4, RoI Heads: 1e−3.
 Weight decay: 0.0005.

 Dataset & Validation:
 Fine-tuned on COCO-Stuff dataset with 9,000 train and validation on 1,000 images.
 Performance metrics:
 mAP: 0.5564 (IoU 0.3 & Confidence 0.3), 0.3239 (IoU 0.4 & Confidence 0.4), 0.2100 (IoU 0.5 & Confidence 0.5).

Performance & Observations

 Achieved strong detection for natural elements and key object classes.
 Variability in detection across some classes remains an area for improvement.

Technologies Used

 Framework: PyTorch
 Hardware:
 Warmup Training: NVIDIA L4 GPU (24GB) with 53GB RAM.
 Fine-Tuning: NVIDIA A100 GPU (40GB) with 80GB RAM.
Note: Mixed Precision Training for Memory and Speed Optimization

Future Scope

 Use advanced augmentation techniques to enhance detection robustness.
 Experiment with larger datasets and ensemble models for better accuracy.
 Address variability with targeted training for specific classes.

 ![image](https://github.com/user-attachments/assets/cbf477ac-cd4f-4401-8a28-94d7065b0cf9)

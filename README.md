# Point Cloud Adversarial Examples by Optimizing Point Intensity Values

### Authors:
- Vivek Reddy Gangula, University of Florida
- Kondreddy Rohith Sai Reddy, University of Florida
- Satya Aakash Chowdary Obellaneni, University of Florida
- Kushi Vardhan Reddy Pasham, University of Florida

## 1. Introduction
This project investigates the vulnerabilities of point cloud-based object detection systems, particularly in autonomous vehicles, against intensity-based adversarial attacks. Unlike traditional adversarial methods that modify the spatial components of point clouds, we focus on manipulating intensity values to mislead object detection models such as PointRCNN.

## 2. Background and Related Work
### Point Cloud-based Object Detection:
- Utilized in autonomous vehicles, drones, virtual reality, and mapping.
- Traditional attacks alter spatial coordinates (x, y, z) to generate adversarial examples.
- Our research explores modifying intensity values instead of geometric structures.

### Adversarial Attacks:
- Aim to mislead detection models by altering input data.
- Can cause models to misinterpret, misclassify, or completely ignore critical objects.
- Our method introduces intensity-based perturbations and evaluates their effectiveness.

## 3. Methodology
### Threat Model
- Assumes attackers can modify point cloud data and have black-box access to the detection model.
- Focuses on intensity manipulations that do not change spatial structures, making attacks harder to detect.

### Data Preparation
- Uses the KITTI dataset, containing LiDAR-generated 3D point clouds.
- Each data point consists of (x, y, z) coordinates and intensity values.

### Model Training
- The PointRCNN model is trained on KITTI dataset for 3D object detection.
- Segments the point cloud into foreground and background and refines object proposals.

### Object Selection using Open3D
- Open3D is used to identify and isolate objects like cars, cyclists, and pedestrians.

### Intensity Manipulation and Evaluation
- The Iterative Gradient Method perturbs intensity values to create adversarial examples.
- The modified point cloud is evaluated using PointRCNN to measure changes in confidence scores.

## 4. Experimental Results
- Detection accuracy varies across different distances and iterations.
- Accuracy for cyclists, pedestrians, and cars decreases with increased perturbation and distance. Despite iterative adversarial attacks, PointRCNN shows robustness to intensity-based perturbations.

## 5. Analysis and Discussion
- Intensity-based attacks had limited impact, demonstrating the robustness of deep learning models. Objects farther from the sensor showed higher vulnerability to misclassification.
- Future research should investigate combined spatial and intensity perturbations to develop stronger adversarial attacks.

## References
1. Yulong Cao et al. Adversarial sensor attack on lidar-based perception in autonomous driving. 2019.
2. Xiaozhi Chen et al. Multi-view 3d object detection network for autonomous driving. 2017.
3. Loic Landrieu et al. Large-scale point cloud semantic segmentation with superpoint graphs. 2018.
4. Xinke Li et al. Pointba: Towards backdoor attacks in 3d point cloud. 2021.
5. Daniel Liu et al. Extending adversarial attacks and defenses to deep 3d point cloud classifiers. 2019.
6. Charles R. Qi et al. Frustum pointnets for 3d object detection from rgb-d data. 2018.
7. Charles R. Qi et al. Pointnet: Deep learning on point sets for 3d classification and segmentation. 2017.
8. Shaoshuai Shi et al. Pointrcnn: 3d object proposal generation and detection from point cloud. 2019.
9. Chong Xiang et al. Generating 3d adversarial point clouds. 2019.
10. Hengshuang Zhao et al. Pointweb: Enhancing local neighborhood features for point cloud processing. 2019.
11. Yin Zhou et al. Voxelnet: End-to-end learning for point cloud based 3d object detection. 2018.

## Requirements
- Python 3.8+
- Open3D
- PyTorch
- NumPy
- KITTI Dataset

## Acknowledgements
We thank the University of Florida for providing resources and support for this research.

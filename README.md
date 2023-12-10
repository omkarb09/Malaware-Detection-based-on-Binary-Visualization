# Malware-Detection-based-on-Binary-Visualization

## Introduction
This project aims to effectively classify files as malware or benign files using Convolutional Neural Network (CNN) models Inception V3 and ResNet-50 by retraining them on custom generated dataset.

## Dataset
A total of 8000 Benign and malicious EXE files (4000 each) were collected from online sources and their binary visualizations were created using following tool:
https://binvis.io/#/
The 8000 images generated using the above tool were used in the dataset.

### Binary visualizations of 3 sample benign EXE files from our dataset
![MixCollage-10-Dec-2023-12-01-PM-5695](https://github.com/omkarb09/Malaware-Detection-based-on-Binary-Visualization/assets/44408619/3704f771-aee1-459f-b082-2afda7907695)

### Binary visualizations of 3 sample malware EXE files from our dataset
![MixCollage-10-Dec-2023-11-55-AM-7794](https://github.com/omkarb09/Malaware-Detection-based-on-Binary-Visualization/assets/44408619/7817ea74-31ec-48e0-a1b0-746b60255c05)

## Implementation
The project initiated with the conversion of executable files into images, followed by resizing to 250 by 250 pixels for enhanced feature extraction. The selected models, InceptionV3 and ResNet, underwent configuration with additional layers, including flattened, dense, dropout, and output layers. The architectures were finalized, accommodating the increased image dimensions. The models featured a convolutional base, a flattened layer, a dense layer with 256 units and ’relu’ activation, a dropout layer with a 50% rate, and a dense output layer with ’sigmoid’ activation. Both models were compiled using the Adam optimizer and binary cross-entropy loss, with accuracy as the monitored metric. The images were organized into training and validation sets, each with a batch size of 32. There were 6000 images used for training, 3000 benign and 3000 malware. Likewise, there were 1000 images used for validation, 500 each. The training process spanned 100 epochs, allowing the models to iteratively learn and adjust their parameters to optimize predictive performance. There were a total of 1000 images used for testing, 500 malware and 500 benign.

## Results
### Inception V3: Confusion Matrix and Classification Report

![image](https://github.com/omkarb09/Malaware-Detection-based-on-Binary-Visualization/assets/44408619/9c567a51-8a12-484d-80a4-8b29779b19e2)
![image](https://github.com/omkarb09/Malaware-Detection-based-on-Binary-Visualization/assets/44408619/05c0f432-817c-48fa-a641-bcaab18b7a97)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### ResNet50: Confusion Matrix and Classification Report

![image](https://github.com/omkarb09/Malaware-Detection-based-on-Binary-Visualization/assets/44408619/65c0aef0-2af8-41e2-908f-584460804e3d)
![image](https://github.com/omkarb09/Malaware-Detection-based-on-Binary-Visualization/assets/44408619/7dd84a91-f933-48e2-8d13-42107fdfa52e)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### ROC Curve for our malware detection models
![image](https://github.com/omkarb09/Malaware-Detection-based-on-Binary-Visualization/assets/44408619/b20b5d40-4f3b-4c7c-9049-95e8b23c0939)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Performance comparison with SOINN
![image](https://github.com/omkarb09/Malaware-Detection-based-on-Binary-Visualization/assets/44408619/ce20ceaa-7e10-4d1b-8efc-b9f05befa083)

## Conclusion
In conclusion, this project contributes to advanced malware detection by combining innovative data preprocessing and CNN models. The choice between InceptionV3 and ResNet-50 depends on specific considerations. Future work may explore model generalization and the integration of additional features for comprehensive malware detection. Overall, this project marks a significant step forward in enhancing cybersecurity through advanced and reliable malware detection methods. In the future, since the accuracy of both models was so high, future research could train the same base models on different file types to see if the high-accuracy results would be repeated. The SOINN multiple-file-type classification model had lower accuracy overall than on individual file types. Based on the results from the retrained Inception V3 and ResNet50 models, having dedicated models for respective file types would likely be better than having a common model for all file types. However, further study would be necessary to prove this.

## References
[1] [n. d.]. Advanced guide to inception V3 | cloud TPU | google cloud. https:
//cloud.google.com/tpu/docs/inception-v3-advanced. Accessed: 2023-11-29.
[2] [n. d.]. Benign EXE Files Dataset. https://github.com/bormaa/Benign-NET/tree/
main. Accessed: 2023-11-29.
[3] [n. d.]. binvis.io visual analysis of binary files. https://Binvis.io. Accessed:
2023-11-29.
[4] [n. d.]. Malware EXE Files Dataset. https://github.com/iosifache/DikeDataset.
Accessed: 2023-11-29.
[5] [n. d.]. ResNet-50: Understanding Residual Networks in Deep Learning. https:
//datagen.tech/guides/computer-vision/resnet-50/. Accessed: 2023-11-29.
[6] Irina Baptista, Stavros Shiaeles, and Nicholas Kolokotronis. 2019. A Novel Malware
Detection System Based On Machine Learning and Binary Visualization. CoRR
abs/1904.00859 (2019). arXiv:1904.00859 http://arxiv.org/abs/1904.00859
[7] Kaiming He, Xiangyu Zhang, Shaoqing Ren, and Jian Sun. 2016. Deep Residual
Learning for Image Recognition. In 2016 IEEE Conference on Computer Vision and
Pattern Recognition (CVPR). 770–778. https://doi.org/10.1109/CVPR.2016.90

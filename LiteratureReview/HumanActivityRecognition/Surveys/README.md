# Human Activity Recognition - Surveys

## Survey on DNN for HAR (2021)

FUQIANG GU, MU-HUAN CHUNG, MARK CHIGNELL, SHAHROKH VALAEE, BAODING ZHOU, & XUE LIU. (2021). A Survey on Deep Learning for Human Activity Recognition. ACM Computing Surveys, 8, 1–34. https://doi.org/10.1145/3472290. [SurveyDeepLearning](SurveyDeepLearning.pdf).

### Why DNN for HAR

Conventional machine learning methods for HAR are laborious, errorprone, and challenging. Instead, deep learning methods are very useful for HAR and can benefit HAR from several aspects.

1. First, it relieves the effort of manually designing features, which often requires expert knowledge.
1. Second, it has shown better accuracy in HAR than conventional methods [69, 160, 260].
1. Third, it has the ability to learn from unlabeled data, which is important and useful for HAR, since it is unpractical to obtain a large amount of labeled activity data.
1. Fourth, it has the powerful capability of learning useful features from raw data and can deal with activity related data from different people, different device models, and varying device poses.

> Deep generative models aim to learn useful representations of data via unsupervised learning or to learn the joint probability distribution of data and their associated classes [184]. Popular generative models are **Restricted Boltzmann Machines (RBMs)** [86], autoencoders [216, 219], **Generative Adversarial Networks (GANs)** [65], and their variants. Discriminative models aim to learn the conditional probability distribution of classes on the data, in which the label information is available directly or indirectly [239]. Popular deep discriminative models are **Convolutional Neural Networks (CNNs)** [62, 106, 178], **Recurrent Neural Networks (RNNs)** [20, 186], and their variants. Deep hybrid models combine a generative model and a  discriminative model where the outcome of the generative model is often used as the input to the discriminative model for classification or regression [52]. These models were originally proposed for processing images, video, speech, and audio, but they can also be applied to other domains such as activity recognition [150, 181, 244] and indoor localization [67, 71].

### Terminalogy

- `Action` means something that is done;
- `Activity` represents the state of being actively occupied, brisk or vigorous action;
- `Behavior` depicts the manner of conducting oneself in the external relations of life

### What sensors are typically used

|Type|Description|Pro/Con|
|-----|---------|--------|
|Ambient sensors| installed at fixed locations (e.g., WiFi access point)| non-intrusive & multi-agent. poor coverage|
|Wearable sensors| carried instruments (e.g., smart phone) | high-coverage & accuracy. single agent|

![sensors.png](sensors.png)

### Preprocessing phase

- `Segmentation` except for images you need multiple readings for HAR
- `Scaling` raw data is crucial to accelerate training times and avoid int overflow issues
- `Spline interpolation` normalizes sampling rates across multiple sensors
- `Autoencoders` require stable inputs but recent models can support irregular time intervals
- `Transforming` typically PCA whitening the input (called sphering) and time-series variation representations
- `Noising` content improves the accuracy of the DNN (or Kalman filter to denoise)

### What DNN do people use

- RBM-based Models (deprecated: training complexity)
  - Deep Belief Networks (DBNs) [19, 84]: One of the first successful HAR solutions
  - Deep Boltzmann Machines (DBMs) [185]: Generative model with simplier structure than DBNs
  - Convolutional Boltzmann Machines (CBMs)
- Autoencoders (best for non image data)
  - Deterministic units instead of stochastic units like RBM)
  - Originally for dimensionality reduction (like PCA)
  - Allows nonlinear encode/decode functions for powerful generalization
  - Types
    - Spare autoencoders (SAE)
    - Denoising autoencoders (DAE)
    - Variation autoencoder (VAE)
- Convolutional Neural Networks (CNN) (best for image data)
  - Basic CNNs usually have four types of layers: convolution layer, pooling layer, detector layer (e.g., ReLU layer), and fully connected layer(a layer in general neural networks)
  - Overall, CNNs are suitable for dealing with data with a known, grid-like topology (e.g., images, time-series data that can be considered as one-dimensional (1D) grid sampling at regular time intervals). However, CNNs may not work well on processing sequential data
- Recurrent Neural Networks
  - RNNs are favorable for dealing with sequential data (e.g., speech, accelerometer readings)
  - Gated Recurrent Units (GRUs) [40, 41], which can adaptively capture sequential dependencies
  - Deep RNN (DRNN) consisting of LSTMs to recognize the activities from several open public datasets. They demonstrated that the unidirectional DRNN outperforms the bidirectional DRNN and the cascaded DRNN
- Generative Adversarial Networks
  - A GAN consists of a generator and a discriminator. The main task of the generator is to learn the data distribution so that it can generate samples to deceive the discriminator. By contrast, the discriminator examines samples to recognize whether they are from real data (training data) or fake data (produced by the generator).
  - Conditional GAN (CGAN) [137] controls the data generation process with auxiliary information (denoted by `c`).
  - Least Squares GAN (LSGAN) [132] uses the least squares loss function for the discriminator rather than the sigmoid cross entropy loss function used in the basic GAN.
  - To date, few works have used GANs and their variants for HAR, but they have great potential to be widely used in HAR as collecting labeled data in HAR is challenging and costly
  - Overall, GANs are suitable for the scenarios where labeled data are few. Existing GAN-based works for HAR use mostly videos or images.

![dl_methods.png](dl_methods.png)

### What public datasets are available

![har_datasets.png](har_datasets.png)

## Survey on HAR using Sensors (2021)

Banjarey, K., Prakash Sahu, S., & Kumar Dewangan, D. (2021). A Survey on Human Activity Recognition using Sensors and Deep Learning Methods. 2021 5th International Conference on Computing Methodologies and Communication (ICCMC), Computing Methodologies and Communication (ICCMC), 2021 5th International Conference On, 1610–1617. https://doi.org/10.1109/ICCMC51019.2021.9418255. [HAR_with_Sensors.pdf](HAR_with_Sensors.pdf)

> One of the most difficult challenges in the field of computer vision is human activity recognition (HAR). The main purpose of intelligent video system is to determine the actions and activities of the individual. However, due to few other unresolved issues including sensor mobility, sensor positioning, contextual setting, and implicit changeability, it remains a difficult task.

HAR processes start with preprocessing the data (e.g., background removal or bounding box creation). Multi-camera systems must also calibrate coordinates for 3D human pose estimation. Next, software detects the joints and evaluates their changes over several frames. Using unsupervised algorithms is useful, but restricts the action space. Meanwhile, supervised algos require specialized datasets which are difficult to create.

### What methods are researchers using

- Pose estimation (vision-based)
  - In a `bottom-up approach` the model detects every key-point in a given image and then tries to put-together the groups of key-points into skeletons for different targets.
  - In the `top-down approach` is the opposite, the network firstly uses an object detector to draw a box around each of the target objects, and then try to guess the keypoints inside every cropped area.
  - Default solution is CNN algos
    - DCNN you increase the number of layers so we improve the quality of images and rate of convergence. After increasing the number of layers in CNN it is called deep CNN
    - Region-based Convolutional Neural Networks (R-CNN) take an image as an input and output a series of bounding boxes, each of which includes an entity and the object's type, such as car or pedestrian.
    - Faster R-CNN is a related object tracking algorithm to R-CNN. Compared to R-CNN and Fast R-CNN, this algorithm uses area proposal networks (RPNs)
  - RNNs are also popular (e.g., LTSMs)
- Wearable devices
  - Deep Restricted Boltzmann Machine Method.
  - Deep Autoencoder.
  - Sparse Coding Method.
  - Stacked Deep Gaussian Method.

### What limitations exist

- Model genre has a significant influence on AR execution
- Number of subjects & diversersity
- Data collection methodology
  - Completely natural
  - semi-natural
  - laboratory
  - sensors

## Learning Models for HAR (2021)

Khan, N. S., & Ghani, M. S. (2021). A Survey of Deep Learning Based Models for Human Activity Recognition. Wireless Personal Communications: An International Journal, 120(2), 1593–1635. https://doi.org/10.1007/s11277-021-08525-w. [LearningModels.pdf](LearningModels.pdf).

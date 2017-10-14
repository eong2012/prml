# Multimodal fully convolutional network for SEMANTIC SEGMENTATION using Keras.
Keras implementation of Fully convolutional Network (FCN-32s)trained to predict semantically segmented images of forest like images with rgb & nir_color input images.
(check out the presentation @ https://docs.google.com/presentation/d/1z8-GeTXvSuVbcez8R6HOG1Tw_F3A-WETahQdTV38_uc/edit?usp=sharing)

---

###### Note:
Do the following steps after you download the dataset before you proceed and train your models.

1. run preprocess/process.sh         (renames images)
2. run preprocess/text_file_gen.py   (generates txt files for train,val,test used in data generator)
3. run preprocess/aug_gen.py         (generates augmented image files beforehand the training, dynamic augmentation in runtime is slow an often hangs the training process)
---
The Following list describes the files :

Improved Architecture with Augmentation & Dropout

1. late_fusion_improveed.py            (late_fusion FCN TRAINING FILE, Augmentation= Yes, Dropout= Yes)
2. late_fusion_improved_predict.py     (predict with improved architecture)
3. late_fusion_improved_saved_model.hdf5 (Architecture & weights of improved model)

Old Architecture without Augmentation & Dropout

4. late_fusion_old.py                  (late_fusion  FCN TRAINING FILE, Augmentation= No, Dropout= No)
5. late_fusion_old_predict.py()        (predict with old architecture)
6. late_fusion_improved_saved_model.hdf5 (Architecture & weights of old model)
---


### Architecture:
![Alt text](/Arc.png)
Architecture Reference (first two models in this link): http://deepscene.cs.uni-freiburg.de/index.html

---
### Dataset:
![Alt text](/DS.png)
Dataset Reference (Freiburg forest multimodal/spectral annotated): http://deepscene.cs.uni-freiburg.de/index.html#datasets

---
### Training:
Loss : Categorical Cross Entropy

Optimizer : Stochastic gradient descent with lr = 0.008, momentum = 0.9, decay=1e-6
---
### Results:

---

# NOTE:
This following files in the repository ::

1.Deepscene/nir_rgb_segmentation_arc_1.py :: ("CHANNEL-STACKING MODEL") 
2.Deepscene/nir_rgb_segmentation_arc_2.py :: ("LATE-FUSION MODEL")
3.Deepscene/nir_rgb_segmentation_arc_3.py :: ("Convoluted Mixture of Deep Experts (CMoDE) Model")

are the exact replicas of the architectures described in Deepscene website.

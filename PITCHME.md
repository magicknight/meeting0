---
marp: true
title: Towards an Inline X-ray Inspection Software Platform
description: Progress and plans
theme: uncover
paginate: true
_paginate: false
---

![bg](./assets/gradient.jpg)

# <!--fit-->Towards an Inline X-ray Inspection Software Platform

 Progress and plans

###### Zhihua Liang ######
###### visionlab ######
###### 20-12-2019

<style scoped>a { color: #eee; }</style>

---

![30%](https://img.favpng.com/19/0/20/machine-learning-deep-learning-with-python-artificial-intelligence-png-favpng-qFCv7GVnQNDpErJCX6ukpSHLw.jpg)
##### <!--fit--> Determine the orientation and position with deep learning 

Resnet + Fine tuning 

---

![bg right 50%](./assets/model.png)

## **[Restnet50](https://en.wikipedia.org/wiki/Residual_neural_network)**

#### A 50-layers convolutional neural network

[![Deploy to Netlify h:1.5em](https://camo.githubusercontent.com/52feade06f2fecbf006889a904d221e6a730c194/68747470733a2f2f636f6c61622e72657365617263682e676f6f676c652e636f6d2f6173736574732f636f6c61622d62616467652e737667)](https://colab.research.google.com/drive/1-QSgNoGSAcr0TTpIYUFQUCoWcrye5-sy)

---

![bg right 10%](./assets/model.png)

### **[Training](https://en.wikipedia.org/wiki/Residual_neural_network)**

###### training a ResNet-50 on a single GPU took ~14 days (10^18 single precision ops)


[![Deploy to Netlify h:1.5em](https://camo.githubusercontent.com/52feade06f2fecbf006889a904d221e6a730c194/68747470733a2f2f636f6c61622e72657365617263682e676f6f676c652e636f6d2f6173736574732f636f6c61622d62616467652e737667)](https://colab.research.google.com/drive/1-QSgNoGSAcr0TTpIYUFQUCoWcrye5-sy)

---

![bg right 100%](./assets/head.png)

### **[Fine tuning](https://en.wikipedia.org/wiki/Residual_neural_network)**

###### Setp 0, get the resnet50 which traned on imagenet without the head layers, then add our own head to it.

###### Step 1, Freeze the body layers, trains the head layers for 10 epochs

###### Step 2, Train all the layers for 100 epochs

[![Deploy to Netlify h:1.5em](https://camo.githubusercontent.com/52feade06f2fecbf006889a904d221e6a730c194/68747470733a2f2f636f6c61622e72657365617263682e676f6f676c652e636f6d2f6173736574732f636f6c61622d62616467652e737667)](https://colab.research.google.com/drive/1-QSgNoGSAcr0TTpIYUFQUCoWcrye5-sy)

---

![bg right 100%](/assets/nvidia.png)
### **[Nvidia P100 GPU](https://www.nvidia.com/en-us/data-center/tesla-p100/)**

##### ~ 20 minutes per epoch
##### 100 epoch = 2000 m =  33 hours ~ one and half day
---

![bg right 100%](/assets/prediction.png)
### **[Euler angles](https://en.wikipedia.org/wiki/Euler_angles)**

##### $\varphi$: $0\degree \to 360\degree$
##### $\theta$:  $-10\degree \to 10\degree$
##### $\psi$:  $-10\degree \to 10\degree$
---

![bg right 37%](/assets/predic.png)
### **[Mean Absolute Error](https://en.wikipedia.org/wiki/Mean_absolute_error)**

##### $\varphi$: 0.14642
##### $\theta$:  0.01692
##### $\psi$:  0.01699


---

![bg](/assets/Framwork.png)

---

### <!--fit--> :ok_hand:

---

![bg 40% opacity blur](./assets/Sinterklaas_2007.jpg)

### Happy Christmas ([@saibaster](https://twitter.com/saibaster))

https://gitlab.com/saibaster


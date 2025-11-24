# **Add-ViT (2024) – Reproduction of Vision Transformer Baseline on CIFAR-10**

**Deep Learning – Project Part 1 Submission**

### **Group Members**

| Name                  | Roll Number |
| --------------------- | ----------- |
| **Romaisa Ahmad**     | 21i-1702    |
| **Masroor Bin Rehan** | 21i-1707    |
| **Arsalan Shabbir**   | 21i-1739    |

---

# **1. Selected Research Paper**

**Title:** *Add-ViT: CNN–Transformer Hybrid Architecture for Small Data Paradigm Processing*
**Authors:** Zheng Liu et al.
**Journal:** Neural Processing Letters (Springer)
**Publication Year:** **2024**
**Peer-reviewed:** ✔ Yes
**Link:** [https://link.springer.com/article/10.1007/s11063-024-11643-8](https://link.springer.com/article/10.1007/s11063-024-11643-8)
**Local PDF:** See `Add-ViT.pdf` (optional)

This paper proposes **Add-ViT**, a hybrid convolution + Vision Transformer architecture specifically designed to improve performance on **small datasets**, especially **CIFAR-10** and **CIFAR-100**.

---

# **2. Project Objective (Part 1)**

In **Part 1**, our goal was to:

### **✔ Select a 2024 peer-reviewed deep learning paper**

### **✔ Reproduce part of its experimental setup**

### **✔ Train a baseline Vision Transformer model on CIFAR-10**

### **✔ Report the reproduced results**

### **✔ Prepare the code and repository for Part 2**

The paper includes baseline Vision Transformer (ViT) results on CIFAR-10.
For Part-1, we replicated the **baseline ViT experiment** before implementing Add-ViT improvements in Part-2.

---

# **3. Domain**

### **Computer Vision**

The paper focuses on:

* Image classification
* Vision Transformers (ViT)
* Small-scale dataset performance
* Hybrid CNN-Transformer architectures

---

# **4. Dataset Used**

### **CIFAR-10**

* 60,000 images
* 10 classes
* 32×32 resolution
* Standard train/test split (50k/10k)

In our preprocessing pipeline:

* Images resized to 224×224 (for ViT)
* Normalized with CIFAR-10 mean/std
* Augmentation: Random Horizontal Flip

Dataset was loaded through **torchvision**, no manual download required.

---

# **5. Model Architecture (Reproduced)**

To reproduce part of the paper’s methodology, we trained the following:

### **Vision Transformer – ViT-Base Patch16-224**

* ~86M parameters
* Trained **from scratch**, as done in the paper
* No ImageNet pretrained weights used
* AdamW optimizer
* CrossEntropy loss
* Batch size: 64
* Resolution: 224×224

 Note:
ViT-Base is computationally heavy, and the paper reports difficulty with training ViT on small datasets — consistent with our results.

---

# **6. Training Configuration**

| Setting       | Value                                 |
| ------------- | ------------------------------------- |
| Optimizer     | AdamW                                 |
| LR            | 1e-4                                  |
| Weight Decay  | 0.05                                  |
| Epochs        | 3 (for fast reproducibility in Colab) |
| Device        | Google Colab GPU (T4)                 |
| Loss Function | CrossEntropyLoss                      |
| Model Save    | `outputs/best_vit_cifar10.pth`        |

---

# **7. Reproduced Results**

These are the results obtained from our Colab execution:

| Epoch | Train Accuracy | Test Accuracy |
| ----- | -------------- | ------------- |
| 1     | 36.33%         | 42.01%        |
| 2     | 43.75%         | 50.60%        |
| 3     | 53.88%         | **55.65%**    |

### **🔹 Final Best Test Accuracy: 55.65%**

This aligns with the known difficulty of training large ViTs from scratch on small datasets — exactly the motivation of the Add-ViT paper.

The paper’s Add-ViT model reaches **94–95%**, whereas ViT-Base without pretraining performs significantly lower, validating our reproduced results.

---



#  **8. What Will Be Done in Part 2**

In Project Part-2, we will:

### ✔ Implement the **Add-Embedding** module

### ✔ Implement **Add-Conv** (depthwise + pointwise)

### ✔ Implement **PMSA** attention

### ✔ Train full Add-ViT model

### ✔ Compare results with baseline ViT

### ✔ Provide improvements + final report

---

#  **9. Acknowledgements**

* Google Colab GPU
* PyTorch
* timm library
* Springer for providing open access to the research paper


Just tell me!

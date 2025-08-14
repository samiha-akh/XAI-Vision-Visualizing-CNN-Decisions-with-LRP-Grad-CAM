
# XAI-Vision: Visualizing CNN Decisions with LRP & Grad-CAM

This project showcases **Explainable AI (XAI)** techniques for interpreting the decision-making process of deep convolutional neural networks (CNNs).  
Using **Layer-wise Relevance Propagation (LRP)** and **Grad-CAM**, we visualize **which parts of an image most influence a CNN's classification**.

Our example uses a **pre-trained VGG16 model** in PyTorch, and can be adapted to any image and class of interest.

---

## Why XAI?

Deep learning models are often seen as **black boxes**. XAI methods:
- Improve **trust** in AI predictions.
- Help **debug** and improve model performance.
- Ensure **ethical and interpretable** AI decisions.
- Provide **visual explanations** for human understanding.

---

## Features

- **Load & preprocess** any RGB image for CNN input.
- Extract **all layers** from VGG16 for fine-grained inspection.
- Compute **LRP relevance maps** to see pixel-level contributions.
- Compute **Grad-CAM heatmaps** to see class-specific important regions.
- Overlay heatmaps on the original image for intuitive interpretation.

---

## How It Works

### **Image Loading & Preprocessing**
- Converts image to RGB.
- Normalizes according to ImageNet statistics.
- Creates a PyTorch tensor with batch dimension.

### **Model Layer Extraction**
- Retrieves VGG16 feature extractor and classifier layers.
- Converts fully connected layers into convolutional equivalents for spatial mapping.

### **Layer-wise Relevance Propagation (LRP)**
- Backpropagates **relevance scores** instead of gradients.
- Distributes relevance from the output back to input pixels.
- Produces a heatmap showing exact pixel contributions.

### **Grad-CAM**
- Uses gradients of the target class score w.r.t. feature maps.
- Weights feature maps by gradient importance.
- Produces a coarse heatmap highlighting important regions for classification.

---

### Results

Grad-CAM
<img width="1463" height="629" alt="image" src="https://github.com/user-attachments/assets/8e1b91aa-41fe-4e9a-948e-6f968a964d2e" />

LRP
<img width="1334" height="615" alt="image" src="https://github.com/user-attachments/assets/5905aa25-fdf8-44d6-ba64-e79df22ea948" />

After Transformations (Affine, RGB/BGR, Distracting Text)
<img width="1586" height="663" alt="image" src="https://github.com/user-attachments/assets/886c89ed-2feb-4db0-a0be-aa001fbba757" />

After Masking


<img width="649" height="654" alt="image" src="https://github.com/user-attachments/assets/cf368c26-e247-447a-b045-2d4176448f9b" /> 
<img width="679" height="321" alt="image" src="https://github.com/user-attachments/assets/18cc6167-2c4d-47f9-95ab-5ebfffa0a2fe" />




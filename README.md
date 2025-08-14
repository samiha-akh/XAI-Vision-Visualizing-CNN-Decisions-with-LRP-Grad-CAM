
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


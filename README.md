# Group 6: Noise Reduction Using Median and Bilateral Filters

## Project Overview
This project demonstrates and compares the effectiveness of **Median** and **Bilateral** filters for image noise reduction. It explores the theoretical background of these filters, their implementation using **OpenCV**, and visualizes their performance on images corrupted with synthetic noise.

The primary goal is to understand how different filtering techniques handle noise while preserving essential image features like edges and textures.

## Introduction

### Image Noise & Its Impact
Image noise refers to random variations in brightness or color information, often produced by the sensor and circuitry of a scanner or digital camera. Noise can significantly degrade visual quality and adversely affect downstream image processing tasks such as edge detection, segmentation, and object recognition.

### Methods Explored
We focus on two robust non-linear filtering techniques:
1.  **Median Filter**: Excellent for removing **Salt-and-Pepper (Impulse) noise**.
2.  **Bilateral Filter**: A powerful **edge-preserving** smoothing filter that reduces noise while maintaining sharp edges.

---

## Theoretical Background

### 1. Median Filter
The Median Filter is a non-linear digital filtering technique, arguably the best-known order-statistics filter.
*   **Mechanism**: It works by moving through the image pixel by pixel, replacing each value with the **median** value of neighboring pixels (defined by a window or kernel, e.g., 3x3 or 5x5).
*   **Why it works**: By selecting the median (the middle value), extreme outliers (like the white and black dots of salt-and-pepper noise) are effectively removed.
*   **Key Characteristic**: Unlike a Gaussian blur which smooths everything, the median filter preserves sharp edges effectively while removing impulse noise.

### 2. Bilateral Filter
The Bilateral Filter is an advanced non-linear filter that smooths images while **preserving edges**.
*   **Mechanism**: It replaces each pixel's intensity with a weighted average of intensity values from nearby pixels. Unlike standard Gaussian blurring that only considers spatial distance, the Bilateral filter considers **two** factors:
    *   **Spatial Proximity** ($\sigma_d$): How close pixels are to each other (geometric distance).
    *   **Intensity Similarity** ($\sigma_r$): How similar the pixel values are (photometric distance).
*   **Why it works**: Pixels that are spatially close but have very different intensity values (e.g., across an edge) are assigned very low weights. This prevents the "blurring specific" to edges, keeping them sharp while smoothing homogeneous regions.

---

## Implementation Details

### Project Structure
*   `notebook.ipynb`: The core Jupyter Notebook containing:
    *   Theoretical explanations.
    *   Python implementation using OpenCV.
    *   Noise generation functions (Salt-and-Pepper).
    *   Visualization of Original vs. Noisy vs. Filtered images.
*   `content/`: Directory containing test images (e.g., `user3.jpg`).

### Technologies Used
*   **Python 3.x**
*   **OpenCV (`cv2`)**: For image processing algorithms.
*   **NumPy (`numpy`)**: For matrix operations and noise generation.
*   **Matplotlib (`matplotlib`)**: For displaying images within the notebook.

---

##   🚀 Getting Started

### Prerequisites
Ensure you have Python installed. You will need the following libraries:

```bash
pip install opencv-python numpy matplotlib notebook
```

### Running the Project
1.  Results are best viewed in a Jupyter Notebook environment.
2.  Code is contained in `notebook.ipynb`.
3.  Launch Jupyter Notebook:
    ```bash
    jupyter notebook notebook.ipynb
    ```
4.  Run the cells sequentially to observe:
    *   Loading of the original image.
    *   Application of synthetic noise.
    *   Recovery of the image using Median and Bilateral filters.

---

## 📊 Expected Results
*   **Median Filter**: You should observe near-perfect removal of "salt-and-pepper" style blocked noise, with edges remaining relatively sharp compared to a standard box or Gaussian blur.
*   **Bilateral Filter**: You will see significant noise reduction in flat regions while object boundaries and text remain crisp, demonstrating its "edge-aware" capabilities.

---

## 👥 Contributors
**Group 6 - DCIT407 Image Processing**

| Name | ID Number |
|------|-----------|
| Tettey Michael Perry | 11318179 |
| Gabriel Kwame Addo Quainoo | 11298181 |
| Johnson Junior Kreponi | 11205898 |
| Adjei-Gyebi Minta O. | 11040586 |
| Aaron Yeboah | 11124173 |
| Fetus Owusu Badu | 11260007 |
| Thomas Tetteh Lartey | 11223578 |
| Mahfuuz Suhyini Mustapha | 11217289 |
| Fareed Iddrisu Gbeadese | 11354851 |
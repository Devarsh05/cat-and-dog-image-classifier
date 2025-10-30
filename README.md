# 🐶🐱 Cats vs Dogs Image Classification (TensorFlow 2.x)

This project implements a **Convolutional Neural Network (CNN)** using **TensorFlow 2.x and Keras** to classify images of **cats** and **dogs**.  
It was completed as part of a deep learning challenge with the goal of achieving **≥ 63% accuracy** (extra credit for ≥ 70%).

---

## 🚀 Project Overview

The model learns to distinguish cats and dogs by training on labeled images and evaluating its performance on unseen test data.  
To improve generalization, the model uses **data augmentation**, **dropout**, and **regularization** techniques.

---

## 📁 Dataset Structure

```
cats_and_dogs/
│
├── train/
│   ├── cats/
│   └── dogs/
│
├── validation/
│   ├── cats/
│   └── dogs/
│
└── test/
    ├── 0001.jpg
    ├── 0002.jpg
    └── ...
```

- **train/** → images used for model training
- **validation/** → used to validate the model during training
- **test/** → unlabeled images for prediction and evaluation

---

## 🧠 Model Architecture

| Layer                  | Output Shape | Description                      |
| :--------------------- | :----------- | :------------------------------- |
| Conv2D(32, 3×3, ReLU)  | 148×148×32   | Extracts basic image features    |
| MaxPooling2D(2×2)      | 74×74×32     | Reduces spatial size             |
| Conv2D(64, 3×3, ReLU)  | 72×72×64     | Learns deeper patterns           |
| MaxPooling2D(2×2)      | 36×36×64     | Further downsampling             |
| Conv2D(128, 3×3, ReLU) | 34×34×128    | Extracts complex features        |
| MaxPooling2D(2×2)      | 17×17×128    | Reduces dimensionality           |
| Flatten()              | –            | Converts features to 1D          |
| Dense(512, ReLU)       | 512          | Fully connected layer            |
| Dropout(0.5)           | –            | Reduces overfitting              |
| Dense(1, Sigmoid)      | 1            | Outputs probability (dog vs cat) |

**Loss:** `binary_crossentropy`  
**Optimizer:** `adam`  
**Metric:** `accuracy`

---

## 🧩 Data Augmentation

To prevent overfitting, random transformations were applied to training images:

- Rotation (±40°)
- Width & height shift (0.2)
- Shear (0.2)
- Zoom (0.2)
- Horizontal flip
- Fill mode = `nearest`
- Pixel rescaling = `1./255`

---

## ⚙️ Training Configuration

| Parameter  | Value                  |
| :--------- | :--------------------- |
| Batch size | 128                    |
| Image size | 150×150                |
| Epochs     | 15                     |
| Framework  | TensorFlow 2.x / Keras |

---

## 💻 How to Run

1. **Clone the repository**

   ```bash
   git clone https://github.com/<your-username>/cats-vs-dogs-cnn.git
   cd cats-vs-dogs-cnn
   ```

2. **Install dependencies**

   ```bash
   pip install tensorflow matplotlib numpy
   ```

3. **Run in Google Colab or Jupyter Notebook**

   - Open `cats_vs_dogs.ipynb`
   - Run all cells sequentially

4. **View outputs**
   - Accuracy/loss plots
   - Test image predictions
   - Final evaluation (≥63% accuracy = Pass ✅)

---

## 📊 Results

| Metric                        | Value (approx.)  |
| :---------------------------- | :--------------- |
| **Training Accuracy**         | 75–80%           |
| **Validation Accuracy**       | 63–70%           |
| **Test Accuracy (Challenge)** | ✅ Passed (≥63%) |

**Example Output:**

```
Your model correctly identified 68.0% of the images of cats and dogs.
You passed the challenge! 🎉
```

---

## 📈 Accuracy & Loss Plots

Two graphs are generated during training:

- **Training vs Validation Accuracy**
- **Training vs Validation Loss**

👉 _(Optional)_ Add screenshots of your plots to the repo:

```markdown
![Training and Validation Accuracy](images/accuracy_plot.png)
![Training and Validation Loss](images/loss_plot.png)
```

> You can save plots in your notebook using:
>
> ```python
> plt.savefig("images/accuracy_plot.png")
> ```

---

## 🖼️ Predictions Visualization

The model predicts probabilities for test images using the `plotImages()` function.  
Each image is labeled with its predicted class and confidence:

```
85.3% dog
27.4% cat
```

👉 _(Optional)_ Add a screenshot of your predictions:

```markdown
![Model Predictions](images/predictions.png)
```

---

## 🧠 Key Takeaways

- Building and training CNNs with TensorFlow/Keras
- Preprocessing images using `ImageDataGenerator`
- Reducing overfitting with dropout and augmentation
- Evaluating performance visually and quantitatively
- Binary classification using deep learning

---

## 🏁 Challenge Outcome

> **Model Accuracy:** ~68%  
> ✅ **Challenge Passed!**  
> 🌟 _Extra credit possible for ≥70% accuracy_

---

## 👤 Author

**Devarsh Prajapati**  
🎓 Computer Science, York University  
🔗 [LinkedIn](https://www.linkedin.com) • 💻 [GitHub](https://github.com)

---

## 🪪 License

This project is licensed under the **MIT License**.  
Feel free to use, modify, and share for educational purposes.

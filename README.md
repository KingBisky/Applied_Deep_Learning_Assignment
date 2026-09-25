# 🧠 Applied Deep Learning: Waste Image & News Article Classification

## 📖 About This Project

This project was developed for the **IT3381 - Applied Deep Learning** assignment. It explores the application of deep learning to two distinct domains:

* 🖼️ **Computer Vision** — Waste Image Classification
* 📰 **Natural Language Processing (NLP)** — News Article Classification

The goal was to build, train, and compare different deep learning models for image and text classification tasks.

---

## 📁 Repository Structure

```text
Applied_Deep_Learning_Assignment/
│
├── KangBin_244423Q_IT3381_Assignment_Part1_Final.ipynb
│   └── Part 1: Waste Image Classification
│
├── KangBin_244423Q_IT3381_Assignment_Part2_Final.ipynb
│   └── Part 2: News Article Classification
│
├── IT3381_KangBin_244423Q_Report_Final.docx
│   └── Full Assignment Report
│
└── README.md
    └── Project Documentation
```

---

# 🎯 Part 1: Waste Image Classification

## Problem Statement

Effective waste sorting is crucial for recycling and sustainability, but manual sorting is labour-intensive.

This project explores the use of deep learning to automatically classify waste images from a real-world landfill environment.

## 📊 Dataset

**RealWaste — UCI Machine Learning Repository**

* **Images:** 4,752 real-world waste images
* **Classes:** 9
* **Classification Categories:**

  * Cardboard
  * Food Organics
  * Glass
  * Metal
  * Miscellaneous Trash
  * Paper
  * Plastic
  * Textile Trash
  * Vegetation

## 🤖 Models Implemented & Compared

| Model                   | Approach                        | Key Details                                                                                                  |
| ----------------------- | ------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| **Custom CNN**          | From Scratch                    | Baseline CNN architecture trained without pretrained features.                                               |
| **Improved Custom CNN** | Architectural Improvement       | Replaced the `Flatten` → `Dense` structure with `GlobalAveragePooling2D`, reducing parameters by **95.58%**. |
| **VGG16**               | Transfer Learning               | Pretrained VGG16 convolutional base used for feature extraction.                                             |
| **Fine-tuned VGG16**    | Transfer Learning + Fine-Tuning | Higher-level convolutional layers were selectively fine-tuned for the waste classification task.             |

## 📈 Key Results

| Model                   | Test Accuracy |   Macro F1 |
| ----------------------- | ------------: | ---------: |
| **Fine-tuned VGG16**    |    **81.49%** | **0.8180** |
| **Improved Custom CNN** |    **51.05%** | **0.5053** |

### Key Finding

The **fine-tuned VGG16** substantially outperformed the custom CNN.

This demonstrates the effectiveness of **transfer learning**, particularly when working with a relatively small image dataset.

---

# 🎯 Part 2: News Article Classification

## Problem Statement

The large volume of online news creates a need for automated organisation and categorisation.

This project uses deep learning to automatically classify news articles into their respective topics.

## 📰 Dataset

**AG News Classification Dataset — Kaggle**

* **Training Articles:** 120,000
* **Test Articles:** 7,600
* **Classes:** 4

### Categories

* 🌍 World
* ⚽ Sports
* 💼 Business
* 💻 Sci/Tech

## 🤖 Models Implemented & Compared

| Model                           | Approach               | Key Details                                                                                                        |
| ------------------------------- | ---------------------- | ------------------------------------------------------------------------------------------------------------------ |
| **Bidirectional LSTM (BiLSTM)** | Trainable Embeddings   | Recurrent neural network with an embedding layer that learned word representations from the AG News training data. |
| **DistilBERT**                  | Pretrained Transformer | Pretrained DistilBERT model fine-tuned for the 4-class news classification task.                                   |

## 📈 Key Results

| Model                     | Test Accuracy |   Macro F1 |
| ------------------------- | ------------: | ---------: |
| **Fine-tuned DistilBERT** |    **94.24%** | **0.9424** |
| **BiLSTM**                |    **91.25%** | **0.9122** |

### Key Finding

The **fine-tuned DistilBERT** model outperformed the BiLSTM.

Its pretrained contextual language representations were particularly useful for distinguishing between semantically overlapping categories such as **Business** and **Sci/Tech**.

---

# 💻 Tech Stack

| Component            | Technology                               |
| -------------------- | ---------------------------------------- |
| **Language**         | Python                                   |
| **Deep Learning**    | TensorFlow, Keras                        |
| **NLP**              | Hugging Face `transformers` / DistilBERT |
| **Data Handling**    | Pandas, NumPy                            |
| **Image Processing** | Pillow (PIL)                             |
| **ML Utilities**     | Scikit-learn                             |
| **Visualization**    | Matplotlib                               |
| **Environment**      | Jupyter Notebook / Google Colab          |

---

# 💡 Key Insights & Takeaways

### 1. Transfer Learning is Highly Effective

For the waste image classification task, pretrained **VGG16** features provided a substantial performance improvement over a CNN trained from scratch.

### 2. Architectural Efficiency Matters

Replacing the `Flatten` → `Dense` architecture with `GlobalAveragePooling2D` drastically reduced the number of parameters while improving validation performance.

### 3. Pretrained Transformers Perform Strongly in NLP

Fine-tuned **DistilBERT** achieved higher classification performance than the BiLSTM by leveraging pretrained contextual language representations.

### 4. Model Complexity vs Performance

The higher-performing models were considerably larger than their simpler counterparts:

| Model          | Approx. Parameters |
| -------------- | -----------------: |
| **Custom CNN** |             ~0.57M |
| **BiLSTM**     |             ~1.39M |
| **VGG16**      |            ~14.78M |
| **DistilBERT** |            ~66.96M |

This highlights an important trade-off between **model performance, computational resources, and model complexity**.

---

# 🚀 How to Run

## 1. Clone the Repository

```bash
git clone <YOUR-GITHUB-REPOSITORY-URL>
cd Applied_Deep_Learning_Assignment
```

## 2. Install the Required Libraries

```bash
pip install tensorflow transformers scikit-learn pandas numpy matplotlib Pillow
```

## 3. Open the Notebooks

The notebooks can be opened using either:

* **Google Colab**
* **Jupyter Notebook**
* **JupyterLab**

## 4. Run the Notebooks

Run the notebook cells sequentially.

The notebooks contain the required preprocessing, model construction, training, evaluation, and visualisation steps.

> **Note:** Dataset availability and download/setup requirements may vary depending on the environment.

---

# 📓 Notebooks

### Part 1 — Waste Image Classification

`KangBin_244423Q_IT3381_Assignment_Part1_Final.ipynb`

Covers:

* Dataset preparation
* Image preprocessing
* Custom CNN development
* CNN architecture improvement
* VGG16 transfer learning
* VGG16 fine-tuning
* Model evaluation
* Performance comparison

### Part 2 — News Article Classification

`KangBin_244423Q_IT3381_Assignment_Part2_Final.ipynb`

Covers:

* Text preprocessing
* Tokenisation
* BiLSTM implementation
* Trainable word embeddings
* DistilBERT fine-tuning
* Model evaluation
* Performance comparison

---

# 📄 Report

The complete assignment report is available in:

```text
IT3381_KangBin_244423Q_Report_Final.docx
```

The report contains the detailed methodology, experiments, results, screenshots, analysis, and discussion for both parts of the assignment.

---

# 👨‍💻 Author

**KangBin**

**Module:** IT3381 — Applied Deep Learning

---

⭐ If you found this project useful, consider giving the repository a star!

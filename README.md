# 🌸 Flower Classification using Machine Learning

A Machine Learning project for classifying Iris flowers into **Setosa, Versicolor, and Virginica** species using their sepal and petal measurements.

This project was completed as part of the **Syntecxhub Machine Learning Internship**.

---

## 📌 Project Overview

The objective of this project is to build and evaluate machine learning classification models that can identify the species of an Iris flower based on four input measurements:

* 🌱 Sepal Length (cm)
* 🌱 Sepal Width (cm)
* 🌸 Petal Length (cm)
* 🌸 Petal Width (cm)

Two classification algorithms were implemented and compared:

* **Logistic Regression**
* **Decision Tree Classifier**

The project includes exploratory data analysis, feature visualization, model training, validation and testing, performance evaluation, confusion matrix analysis, model comparison, and prediction of new flower inputs.

---

## 🎯 Objectives

* Load and understand the Iris dataset
* Perform Exploratory Data Analysis (EDA)
* Analyze feature distributions and relationships
* Visualize feature pairs
* Split the dataset into training, validation, and testing sets
* Train Logistic Regression and Decision Tree models
* Evaluate model performance using:

  * Accuracy
  * Precision
  * Recall
  * F1 Score
* Visualize confusion matrices
* Analyze model misclassifications
* Compare the performance of both models
* Build a prediction interface for new flower measurements
* Implement a simple CLI for new flower prediction

---

## 📊 Dataset

The project uses the **Iris dataset** available through Scikit-learn.

### Features

| Feature      | Description                        |
| ------------ | ---------------------------------- |
| Sepal Length | Length of the sepal in centimeters |
| Sepal Width  | Width of the sepal in centimeters  |
| Petal Length | Length of the petal in centimeters |
| Petal Width  | Width of the petal in centimeters  |

### Target Classes

| Class | Species    |
| ----- | ---------- |
| 0     | Setosa     |
| 1     | Versicolor |
| 2     | Virginica  |

The dataset contains **150 samples**, with **50 samples from each species**.

---

## 🔍 Exploratory Data Analysis

The following EDA steps were performed:

* Dataset shape and structure analysis
* Statistical summary
* Missing-value checking
* Species distribution analysis
* Sepal Length distribution
* Sepal Width distribution
* Petal Length distribution
* Petal Width distribution
* Feature boxplots
* Feature correlation heatmap
* Pairwise feature visualization

### Key EDA Observations

The feature visualizations show that the Iris species have different patterns across their sepal and petal measurements.

In particular, petal-related features provide strong separation between the different flower species, while some overlap can be observed between **Versicolor** and **Virginica**.

---

## ✂️ Data Splitting

The dataset was divided into:

* **60% Training**
* **20% Validation**
* **20% Testing**

Stratified splitting with `random_state=42` was used to maintain class proportions.

---

## 🤖 Machine Learning Models

### 1. Logistic Regression

A Logistic Regression classifier was trained using the four flower measurements.

**Test Accuracy: 96.67%**

### 2. Decision Tree

A Decision Tree classifier was trained with `max_depth=4` to control unnecessary tree growth.

**Test Accuracy: 93.33%**

---

## 📈 Model Performance Comparison

| Model               |   Accuracy |  Precision |     Recall |   F1 Score |
| ------------------- | ---------: | ---------: | ---------: | ---------: |
| Logistic Regression | **96.67%** | **96.97%** | **96.67%** | **96.66%** |
| Decision Tree       | **93.33%** | **93.33%** | **93.33%** | **93.33%** |

The metrics above are calculated on the **test set** using weighted averages for Precision, Recall, and F1 Score.

---

## 🧪 Train, Validation & Test Performance

| Model               | Training Accuracy | Validation Accuracy | Test Accuracy |
| ------------------- | ----------------: | ------------------: | ------------: |
| Logistic Regression |            97.78% |              93.33% |    **96.67%** |
| Decision Tree       |           100.00% |              93.33% |        93.33% |

The Logistic Regression model shows relatively consistent performance across the training, validation, and test sets.

The Decision Tree achieves 100% training accuracy but lower validation and test accuracy, indicating that it fits the training data more closely and shows some indication of overfitting.

---

## 🔲 Confusion Matrix & Misclassification Analysis

### Logistic Regression

The Logistic Regression model correctly classified:

* **10/10 Setosa**
* **9/10 Versicolor**
* **10/10 Virginica**

Only one Versicolor sample was classified as Virginica.

Therefore:

**29 out of 30 test samples were correctly classified.**

---

### Decision Tree

The Decision Tree correctly classified:

* **10/10 Setosa**
* **9/10 Versicolor**
* **9/10 Virginica**

One Versicolor sample was classified as Virginica, and one Virginica sample was classified as Versicolor.

Therefore:

**28 out of 30 test samples were correctly classified.**

### Interpretation

Both models classify **Setosa** very clearly.

The main classification difficulty occurs between **Versicolor and Virginica**, where some feature values overlap. This is reflected in the confusion matrices and explains the small number of misclassifications.

---

## 🌸 New Flower Prediction

An interactive prediction interface was created using `ipywidgets`.

Users can select:

* Sepal Length
* Sepal Width
* Petal Length
* Petal Width

and click **Predict Flower** to obtain:

* Predicted flower species
* Prediction confidence

### Example Input

```text
Sepal Length: 5.1 cm
Sepal Width:  3.5 cm
Petal Length: 1.4 cm
Petal Width:  0.2 cm
```

The trained Logistic Regression model can then predict the corresponding Iris species.

---

## 💻 CLI Prediction

A standalone Python CLI script is also included for predicting a new flower from user-provided measurements.

The user enters:

```text
Enter Sepal Length (cm):
Enter Sepal Width (cm):
Enter Petal Length (cm):
Enter Petal Width (cm):
```

The script returns:

```text
Predicted Species : Setosa
Confidence        : XX.XX%
```

This provides a simple way to test the trained classification workflow with new flower measurements.

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* IPyWidgets
* Google Colab
* Jupyter Notebook
* GitHub

---

## 📁 Project Structure

```text
Flower_Classification_Syntecxhub/
│
├── Flower_Classification_Devadharshini_Syntecxhub.ipynb
└── README.md
```

---

## 🚀 How to Run

### Using Google Colab

1. Open the `.ipynb` notebook in Google Colab.
2. Run the cells sequentially.
3. Perform EDA and model evaluation.
4. Run the prediction interface.
5. Enter new flower measurements.
6. Click **Predict Flower** to obtain the prediction.

### Running the CLI

Run the CLI script and provide the four flower measurements when prompted.

---

## 📌 Conclusion

This project demonstrates an end-to-end Machine Learning classification workflow using the Iris dataset.

The two models were trained and evaluated using training, validation, and test datasets. Logistic Regression achieved a **96.67% test accuracy**, while the Decision Tree achieved **93.33% test accuracy**.

The confusion matrix analysis showed that **Setosa was consistently classified correctly**, while the small number of errors mainly occurred between **Versicolor and Virginica**.

The project also includes an interactive prediction interface and a CLI-based prediction script for testing new flower measurements.

---

## 👩‍💻 Author

**Devadharshini M**

Machine Learning Intern — Syntecxhub

---

## 🏢 Internship

**Syntecxhub — Machine Learning Internship**

Project: **Flower Classification**

GitHub Repository:

`flower_classification_Syntecxhub`

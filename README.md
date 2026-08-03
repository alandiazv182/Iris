# Iris Dataset - K-Means Clustering

## Overview

This project explores the Iris dataset using the K-Means clustering algorithm, an unsupervised machine learning technique.

The goal was to determine whether K-Means could separate Iris flower samples into meaningful groups based only on their measurements:

- Sepal length
- Sepal width
- Petal length
- Petal width

The clustering results were compared with the known species labels to evaluate how well the algorithm was able to identify the different Iris species.

A simple rule-based classifier was also created to compare its performance against the unsupervised K-Means approach.

---

## Dataset

The Iris dataset contains 150 samples from three flower species:

- Iris-setosa
- Iris-versicolor
- Iris-virginica

Each sample contains four numerical measurements:

- Sepal Length (cm)
- Sepal Width (cm)
- Petal Length (cm)
- Petal Width (cm)

The species labels were converted into numerical values:

- Iris-setosa → 0
- Iris-versicolor → 1
- Iris-virginica → 2

---

## Exploratory Data Analysis

The dataset was explored using descriptive statistics, feature distributions and pairplots.

The analysis showed that petal length and petal width provided better separation between species compared with the sepal measurements.

Based on this observation, two K-Means models were evaluated:

1. K-Means using all four features
2. K-Means using only petal length and petal width

---

## Modeling

### Rule-Based Classification

A simple classifier was created using petal length thresholds to predict the Iris species.

The rules were:

- Petal length < 2.5 → Iris-setosa
- Petal length < 4.75 → Iris-versicolor
- Otherwise → Iris-virginica

**Accuracy: 0.946**

---

### K-Means Clustering

Before applying K-Means, the features were standardized using StandardScaler since the algorithm calculates distances between data points.

The elbow method was used to estimate the optimal number of clusters.

**Selected number of clusters: k = 3**

The clustering performance was evaluated using the Adjusted Rand Index (ARI).

Results:

| Model | Adjusted Rand Index |
|---|---:|
| K-Means (all features) | 0.430 |
| K-Means (petal features only) | 0.872 |

---

## Results and Conclusion

The results showed that petal measurements contain most of the information needed to separate the Iris species.

Using only petal length and petal width improved the K-Means performance from an ARI of 0.430 to 0.872. This shows that selecting the most relevant features can improve clustering results.

The rule-based classifier achieved a higher accuracy because it used the observed relationship between petal measurements and species labels. In comparison, K-Means was able to identify similar groups without using the species labels during training.

This project shows the difference between supervised and unsupervised learning approaches. Supervised models use labeled data to make predictions while unsupervised models try to discover patterns within the data.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

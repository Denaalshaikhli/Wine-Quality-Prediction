# Wine Quality Prediction

> README GitHub Project Documentation

This project is a part of the **AAI-500** course in the Applied Artificial Intelligence Program at the **University of San Diego (USD)**.

**Project Status:** Completed

---

## Installation

This project runs in Google Colab or any standard Jupyter environment. All data files are included in the repository.

### Google Colab
The notebook can be opened directly in Google Colab by navigating to:
[Open in Colab](https://colab.research.google.com/drive/1wzfdjvHVafb5mPRJ4Xv8d57WPMnLF7n_#scrollTo=__m_cznUYi95)

All cells run sequentially from top to bottom, with no additional configuration required.

### Local Environment
Install all required dependencies:
```bash
pip install pandas numpy matplotlib seaborn scipy statsmodels scikit-learn
```
Launch the notebook:
```bash
jupyter notebook TeamProject.ipynb
```

---

## Project Intro / Objective

The main purpose of this project is to determine whether the physicochemical properties of Vinho Verde wine, obtained through standard laboratory testing, can reliably predict wine quality classifications assigned by human tasting panels. Expert tasting panels are expensive, time-consuming, and inherently subjective; a data-driven model offers a scalable and objective alternative for winery quality control.

This project applies a complete statistical pipeline connecting all seven modules of AAI-500 to a real-world business problem. The analysis demonstrates that two chemical measurements, **alcohol content (r = +0.44)** and **volatile acidity (r = -0.39)**, drive the majority of the quality signal. The Bayesian Network shows that combining high alcohol with low volatile acidity raises the posterior probability of good quality classification to **88.6%**. The GLM achieves AUC-ROC of **0.8250** on the held-out test set, and the Random Forest classifier achieves the highest accuracy at **78.3%**.

---

## Partners / Contributors

| Name | Role | Sections |
|------|------|----------|
| Tena Alshaikhli | Team Lead | Introduction, Statistical Analysis, Bayesian Network, GLM |
| Roopleen Kaur | Data and Model Analysis | Data Cleaning, EDA, Model Analysis |
| Timothy Hays | Modeling and Testing | Hypothesis Testing, Model Selection, Conclusion |

**GitHub:** https://github.com/Denaalshaikhli/Wine-Quality-Prediction

**Instructor:** Professor Leon Shpaner, University of San Diego

---

## Methods Used

- Descriptive Statistics and Data Collection (Module 1)
- Sampling Distributions and Central Limit Theorem (Module 3)
- Inferential Statistics and Hypothesis Testing (Module 4)
- Bayesian Network Probabilistic Modeling (Module 5)
- Generalized Linear Models with Logit Link Function (Module 6)
- Machine Learning Classification: Random Forest, Gradient Boosting, Logistic Regression, Naive Bayes (Module 7)
- Machine Learning Regression: Linear Regression, Bayesian Ridge (Module 7)
- Data Visualization
- Data Manipulation and Preprocessing

---

## Technologies

- Python 3
- pandas
- numpy
- matplotlib
- seaborn
- scipy
- statsmodels
- scikit-learn
- Google Colab
- Jupyter Notebook
- GitHub

---

## Project Description

### Dataset

| Property | Value |
|----------|-------|
| Source | UCI Machine Learning Repository |
| Citation | Cortez et al. (2009). Decision Support Systems, 47(4), 547-553 |
| Original samples | 6,497 |
| After cleaning | 5,320 |
| Red wine samples | 1,359 |
| White wine samples | 3,961 |
| Features | 11 physicochemical variables |
| Target variable | Quality score 0-10, binarized at threshold 6 |
| Good quality (score >= 6) | 3,332 samples (62.6%) |
| Poor quality (score < 6) | 1,988 samples (37.4%) |

### Research Question

> Can physicochemical properties of wine, measurable through standard laboratory testing, reliably predict whether a wine will be rated as good or poor quality by human tasters?

### Key Results

| Analysis | Key Finding |
|----------|-------------|
| Descriptive Statistics | Alcohol: Good 10.929% vs Poor 9.913% \| Volatile Acidity: Good 0.309 vs Poor 0.403 |
| Central Limit Theorem | SE = 0.1677 from 5,000 samples of n=50 \| Confirms normality of sampling distribution |
| Confidence Intervals | Alcohol Good [10.888, 10.969] vs Poor [9.875, 9.951] — non-overlapping |
| Bayesian Network | High Alcohol + Low VA = 88.6% \| Low Alcohol + High VA = 17.3% |
| GLM (Logistic Regression) | AUC-ROC = 0.8250 \| Accuracy = 0.7556 \| Recall = 0.8419 |
| Best Classifier | Random Forest: Accuracy = 0.783 \| F1 Score = 0.780 |

### Data Dictionary

| Variable | Description | Unit | Type |
|----------|-------------|------|------|
| fixed acidity | Non-volatile acids | g/dm3 | Continuous |
| volatile acidity | Acetic acid — vinegar smell at high levels | g/dm3 | Continuous |
| citric acid | Freshness and flavor | g/dm3 | Continuous |
| residual sugar | Sugar remaining after fermentation | g/dm3 | Continuous |
| chlorides | Salt content | g/dm3 | Continuous |
| free sulfur dioxide | Prevents microbial growth | mg/dm3 | Continuous |
| total sulfur dioxide | Total SO2 (free and bound) | mg/dm3 | Continuous |
| density | Mass per volume | g/cm3 | Continuous |
| pH | Acidity level on 0 to 14 scale | — | Continuous |
| sulphates | Antimicrobial and antioxidant additive | g/dm3 | Continuous |
| alcohol | Alcohol percentage by volume | % | Continuous |
| quality | Sensory score 0 to 10 — TARGET | — | Discrete |

---

## Challenges

- Coordinating a shared Colab notebook across three team members while maintaining section consistency
- The GLM was restructured to train on training data only and evaluate on the held-out test set to ensure proper generalization assessment
- Multicollinearity between density, alcohol, and residual sugar caused an inflated negative coefficient for density in the GLM
- The dataset is limited to Vinho Verde wines from Portugal and may not generalize to other wine varieties or regions

---

## License

This project was created for academic purposes as part of the AAI-500 course at the University of San Diego. The UCI Wine Quality Dataset is publicly available under the Creative Commons Attribution 4.0 International license. Full license details are available at https://archive.ics.uci.edu/dataset/186/wine+quality

---

## Acknowledgments

We thank Professor Leon Shpaner for his guidance throughout the AAI-500 course and for the statistical framework that shaped this analysis. We also acknowledge Paulo Cortez and co-authors for making the Wine Quality Dataset publicly available through the UCI Machine Learning Repository.

---

## References

Agresti, A., & Kateri, M. (2022). *Foundations of statistics for data scientists: With R and Python.* CRC Press.

Cortez, P., Cerdeira, A., Almeida, F., Matos, T., & Reis, J. (2009). Modeling wine preferences by data mining from physicochemical properties. *Decision Support Systems, 47*(4), 547-553. https://doi.org/10.1016/j.dss.2009.05.016

Pedregosa, F., et al. (2011). Scikit-learn: Machine learning in Python. *Journal of Machine Learning Research, 12*, 2825-2830.

UCI Machine Learning Repository. (2009). Wine quality dataset. https://archive.ics.uci.edu/dataset/186/wine+quality

Van Rossum, G., & Warsaw, B. (2001). PEP 8: Style guide for Python code. Python Software Foundation. https://pep8.org

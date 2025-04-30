# 👨‍💼 Employee Attrition Risk Prediction System

Employee attrition poses significant challenges for organizations, including productivity loss and increased hiring costs. Traditional methods are reactive and lack data-driven insights. This project leverages machine learning to predict attrition risk and provides HR professionals with proactive decision-support tools via a web-based system.

## 🔍 Abstract

- Developed a machine learning-based system to predict employee attrition using IBM's HR Analytics dataset.
- Utilized a **Random Forest Classifier** for its robustness and ability to handle mixed data types while preventing overfitting.
- Predictions are categorized into **Low**, **Moderate**, and **High** risk levels based on probability scores.
- Built a user-friendly web interface using **Gradio**, allowing HR personnel to:
  - Input employee details
  - View real-time attrition risk
  - Access insightful visualizations such as pie charts, histograms, and scatter plots.

---

## 🛠️ Tech Stack

| Component           | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| **Language**         | Python 3.8+                                                                 |
| **Libraries**        | `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `gradio`, `opendatasets`  |
| **Model**            | Random Forest Classifier (via scikit-learn)                                 |
| **Frontend**         | Gradio for building a no-code web interface                                 |
| **Model Storage**    | Pickle (to persist and reload trained models)                               |

---

## 📦 Modules

### 📁 1. Data Collection
- IBM HR Analytics dataset downloaded via `opendatasets` from Kaggle.
- Fields include: Age, Department, Education Field, OverTime, Job Role, Gender, etc.

### 🧹 2. Data Preprocessing
- Label Encoding & One-Hot Encoding for categorical variables.
- Normalization using `StandardScaler`.
- Dropped irrelevant features like `EmployeeCount`, `Over18`.

### 🧠 3. Model Training
- Trained a Random Forest Classifier on the cleaned dataset.
- Model is serialized with `pickle` for later inference.

### 🔮 4. Prediction Pipeline
- User inputs (e.g., Age, Department, Gender, OverTime) are preprocessed using the same pipeline.
- Model returns a prediction and corresponding attrition risk category:
  - **Low Risk**: Probability < 0.3
  - **Moderate Risk**: 0.3 ≤ Probability < 0.7
  - **High Risk**: Probability ≥ 0.7

### 📊 5. Visualization
- **Pie Chart**: Department-wise employee distribution.
- **Histogram**: Age distribution.
- **Scatter Plot**: Monthly Income vs Age.
- **Bar Graph**: Avg. Monthly Income by Job Role.

### 🔐 6. Authentication
- Simple login screen with password validation.
- Regex-based password strength checking for enhanced security.

### 🌐 7. Web Interface (Gradio)
- Provides:
  - Login page
  - Input form for predictions
  - Visualizations and insights
- No web development skills required for interaction.

---

## ⚙️ Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/employee-attrition-predictor.git
   cd employee-attrition-predictor

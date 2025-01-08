# Fake Job Post Predictor

## Overview
This project aims to identify fake job postings using machine learning techniques. By analyzing patterns in job descriptions, titles, and metadata, the model predicts whether a job post is real or fake.

---

## Dataset
The dataset contains the following columns:
- **company**: Name of the company posting the job.
- **title**: Title of the job position.
- **description**: Details about the job.
- **salary**: Salary offered for the position.
- **location**: Job location.
- **requirements**: Requirements for the job.
- **contact_email**: Email for contact.
- **urgency**: Urgency or deadlines mentioned.
- **is_fake**: Label indicating whether the job post is fake (`True`) or real (`False`).

---

## Key Observations
The following patterns were commonly observed in fake job posts:
1. **Requirements**: Often state "no experience" required.
2. **Urgency**: Contain words like "immediate" or "urgent".
3. **Email Domain**: Use unprofessional domains (e.g., Gmail, Yahoo).
4. **Location**: Often list "Remote - Anywhere".
5. **Company Name**: Frequently include "International" in the name.

---

## Steps

### 1. Data Preprocessing
- Handled missing values.
- Cleaned text fields (e.g., job descriptions, titles).
- Encoded categorical data.

### 2. Feature Engineering
New features were created based on observed patterns:
- `requirement_no_experience`: Binary feature indicating if "no experience" is mentioned.
- `urgency_immediate`: Binary feature for keywords like "immediate" or "urgent".
- `email_unprofessional_domain`: Binary feature for emails using non-professional domains.
- `location_remote_anywhere`: Binary feature for locations listed as "Remote - Anywhere".
- `company_international`: Binary feature for company names containing "International".

### 3. Model Building
- Split the dataset into training and testing sets.
- Trained a Logistic Regression model as a baseline.
- Optionally used a Random Forest model for improved accuracy.

### 4. Evaluation
Metrics used to evaluate the model:
- **Accuracy**: Overall correctness of predictions.
- **Precision**: Proportion of true positives among predicted positives.
- **Recall**: Proportion of true positives among actual positives.
- **F1 Score**: Harmonic mean of precision and recall.
- **Confusion Matrix**: To visualize true/false positives and negatives.

---

## Visualizations
The following plots were created to understand the data and model:
1. **Feature Distributions**: Count plots for key features grouped by `is_fake`.
2. **Correlation Heatmap**: To show relationships between features and `is_fake`.
3. **Confusion Matrix**: To visualize model performance.
4. **Feature Importance**: For Random Forest to highlight the significance of each feature.

---

## How to Run

1. **Install Dependencies**:
   Ensure the required libraries are installed:
   ```bash
   pip install pandas scikit-learn matplotlib seaborn
   ```

2. **Load the Dataset**:
   - Place your dataset (`job_posts.csv`) in the working directory.
   - Update the file path in the script.

3. **Run the Script**:
   - Execute the Python script to train and evaluate the model.

4. **View Results**:
   - Visualizations and metrics will be displayed in the output.

---

## Results
- The Logistic Regression model achieved an accuracy of approximately X%.
- The Random Forest model achieved an accuracy of approximately Y%.

---

## Future Improvements
- **Additional Features**: Extract more advanced text features using NLP techniques (e.g., TF-IDF, word embeddings).
- **Deep Learning**: Experiment with LSTM or Transformer models for text classification.
- **Deploy Model**: Develop a web app or API for real-time predictions.




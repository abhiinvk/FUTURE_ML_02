# Customer Support Ticket Classification and Prioritization

## Project Overview

This project builds a customer support ticket processing system using Machine Learning and rule-based prioritization. It classifies incoming support requests into categories and suggests a priority level based on predefined business rules.

Developed as part of the **Future Interns Machine Learning Internship — Task 2**.

## Objectives

- Automatically classify support tickets by topic.
- Evaluate the classification model using standard ML metrics.
- Suggest ticket priorities using transparent rules.
- Identify limitations and recommend human review for uncertain or critical cases.

## Dataset

The dataset contains 47,837 documents with two columns:

- `Document`: Support request text.
- `Topic_group`: Labeled support category.

The eight categories are Hardware, HR Support, Access, Miscellaneous, Storage, Purchase, Internal Project, and Administrative rights.

## Technologies Used

- Python
- Pandas
- Scikit-learn
- TF-IDF Vectorization
- Logistic Regression
- Matplotlib
- Jupyter Notebook

## Methodology

1. Inspected the dataset and checked missing values and duplicate labels.
2. Split the data into training and testing sets using an 80/20 stratified split.
3. Converted text into numerical features using TF-IDF with unigrams and bigrams.
4. Trained a Logistic Regression classifier with balanced class weights.
5. Evaluated performance using accuracy, precision, recall, F1-score, and a confusion matrix.
6. Implemented a separate rule-based priority suggestion function.

## Model Performance

| Metric | Result |
|---|---:|
| Test accuracy | 85.45% |
| Macro F1-score | 0.86 |
| Weighted F1-score | 0.85 |
| Test documents | 9,568 |

These results were obtained on the held-out test set. Performance on new real-world support tickets may differ.

## Ticket Prioritization

The prioritization component uses predefined keyword rules to suggest:

- **Critical:** Potential security breaches or major production outages.
- **High:** Issues that completely block work or significantly disrupt operations.
- **Medium:** Other issues requiring assessment.
- **Low:** General questions and non-urgent requests.

This component is a rule-based baseline, not a trained priority classifier. The rules require further validation against real ticket priorities and organizational policies. Human review is important, especially for potentially critical incidents.

## Limitations

- The classification model may confidently misclassify some messages.
- The dataset contains topic labels but no priority labels.
- The prioritization rules have not been formally evaluated against a labeled priority test set.
- Confidence scores are not guarantees of correctness.

## Future Improvements

- Improve classification using error analysis and additional labeled examples.
- Calibrate confidence scores and route uncertain predictions for review.
- Validate prioritization rules against historical ticket outcomes.
- Build a web interface using Flask, Django, or Streamlit.
- Explore a complete support ticket management workflow.

## How to Run

1. Clone or download this repository.
2. Install the required packages:

   `pip install pandas scikit-learn matplotlib jupyter`

3. Place the dataset in the project folder.
4. Open the Jupyter Notebook in VS Code.
5. Run the cells in order to reproduce preprocessing, training, evaluation, and priority examples.

## Conclusion

This project demonstrates how text classification can automate support-ticket categorization and how transparent business rules can provide an initial priority suggestion. It also highlights the importance of evaluating model predictions and distinguishing trained ML outputs from rule-based decisions.

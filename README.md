# Breast Cancer Classification App

This project aims to predict whether a tumor is **benign** or **malignant** based on various features like **radius**, **texture**, **perimeter**, and others, using a **Logistic Regression** model. The model was trained on the **Wisconsin Diagnostic Breast Cancer (WDBC)** dataset. The web application allows users to input tumor measurements through sliders and receive a prediction, along with a visual representation of the input data on a radar chart.

## Project Overview

The app leverages machine learning and web technologies to classify breast tumors into two categories:
- **Benign** (non-cancerous)
- **Malignant** (cancerous)

The app uses **Logistic Regression**, a binary classification model, to make predictions. The tumor measurements are input by users through **Streamlit sliders** in the sidebar, and the results are displayed on the screen. Along with the prediction, the app provides a radar chart visualizing the tumor's features, including:
- **Mean value**
- **Standard Error**
- **Worst value** of the features like 'Radius', 'Texture', 'Perimeter', 'Area', etc.

## Technologies Used

- **Streamlit**: For building the interactive web app.
- **Scikit-learn**: For training and evaluating the logistic regression model.
- **Pickle**: For saving and loading the trained model and scaler.
- **NumPy**: For data manipulation.
- **Pandas**: For data handling and cleaning.
- **Plotly**: For generating the interactive radar chart.

## Features

- **User Input via Sliders**: Users can adjust the tumor measurements via sliders in the sidebar, which are dynamically linked to the prediction.
- **Prediction**: The app predicts whether the tumor is benign or malignant based on the inputs, and displays the probability for both classifications.
- **Radar Chart**: A radar chart that shows the tumor’s measurements in three categories: **Mean value**, **Standard Error**, and **Worst value** for each feature.
- **Interactive Visualization**: The chart is interactive, allowing users to explore the differences in tumor characteristics visually.

## Installation

To run this project locally, follow these steps:

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/cancer-classification-app.git
   cd cancer-classification-app
   ```

2. Create and activate a virtual environment (optional but recommended):

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install the necessary dependencies:

   ```bash
   pip install -r requirements.txt
   ```

4. Make sure to have the trained model and scaler (`model.pkl` and `scaler.pkl`) in the correct folder, as the app loads these using `pickle`.

## How to Run

1. After setting up the environment, start the app using the following command:

   ```bash
   streamlit run app.py
   ```

2. Open your browser and go to `http://localhost:8501` to see the app in action.

## Features Explanation

- **Sliders for Input**: In the sidebar, users can adjust the values of various tumor measurements such as radius, texture, perimeter, and others. These sliders dynamically update the data sent to the model.
  
- **Radar Chart**: The radar chart displays the input data in three categories:
  - **Mean value**: The average measurement of each feature.
  - **Standard Error**: The standard deviation of the measurement across samples.
  - **Worst value**: The highest value of each feature across samples.

- **Prediction and Probabilities**: After the user adjusts the sliders, the app predicts whether the tumor is benign or malignant and shows the probabilities of each outcome.

## Model Explanation

The model used in this project is a **Logistic Regression** classifier, which is well-suited for binary classification tasks. The model was trained on the **WDBC dataset**, which contains features like **radius**, **texture**, **perimeter**, and others, representing tumor characteristics. 

The **scaler** used to normalize the data was also saved using **pickle**, which is applied to user inputs before they are passed to the model for prediction.

## Example

Here’s a walkthrough of how the app works:

1. The user opens the app and sees sliders to adjust various tumor measurements in the sidebar.
2. The user adjusts the sliders to represent the tumor measurements for a new sample.
3. The app dynamically updates the radar chart to show how the new tumor sample compares with the **mean**, **standard error**, and **worst** values of different features.
4. The app predicts whether the tumor is **benign** or **malignant** and displays the prediction along with the probabilities for each outcome.

## Model Deployment

This app has been deployed on [Streamlit Cloud](https://streamlit.io/) and is available for public access. You can use the app to predict tumor classifications in real-time.

## Code Overview

### 1. **app.py** (Main file)
- Contains the logic for loading the model and scaler.
- Handles user input via sliders and updates the prediction.
- Generates and displays the radar chart.

### 2. **style.css** (Styling)
- Contains custom CSS to style the app, including the sidebar, buttons, and radar chart.
- Ensures the app has an attractive and user-friendly interface.

### 3. **model.pkl** (Pickled Model)
- The trained logistic regression model saved using `pickle`.
- Used for making predictions based on user input.

### 4. **scaler.pkl** (Pickled Scaler)
- A fitted `StandardScaler` that ensures input data is properly normalized before being passed to the model.

## Contributing

If you'd like to contribute to the project, feel free to fork the repository, make changes, and submit a pull request. Please ensure to follow the standard code conventions and add appropriate tests if applicable.

## Acknowledgments

- The **WDBC dataset** was used as the source data for training the model. This dataset is publicly available from the UCI Machine Learning Repository.
- **Streamlit** for providing an easy-to-use framework for building interactive applications.
- **Scikit-learn** for providing robust tools for machine learning.

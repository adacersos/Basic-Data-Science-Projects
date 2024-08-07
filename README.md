# Basic-Data-Science-Projects

# Case 1: Stock Price Forecaster

- **Timeline:** January 2024 - February 2024
- **Creator:** Adam Cersosimo

### Overview

This project involves creating an Exponential Smoothing State Space Model (ETS) to predict future stock prices for selected companies based on historical stock price data.

### Key Steps

1. **Data Acquisition and Cleaning**
   - Downloaded 5 years of stock data for Google, Boeing, Netflix, Chipotle, and Tesla from yahoo finance
   - Loaded each dataset into Jupyter Notebooks using Pandas and removed unnecessary columns
   - Isolated the adjusted stock closing price to use in the time series model

2. **Model Development:**
   - Split the Data into training and test sets to create ETS and linear models to see how they perform on test data
   - Implemented the ETS model to predict the next year of stock price for each stock
4. **Results:**
   - Despite the inherent challenges in predicting stock prices accurately, the model demonstrated an ability to identify the general direction of stock price movements
   - MSE was substantially higher for certain stocks which could be attributed to randomness or a higher volatility in the stock

# Case 2: Restaurant Star Ratings Predictor

- **Timeline:** January 2024 - February 2024
- **Creator:** Adam Cersosimo

## Overview

This project serves as a predictor for restaurant star ratings in Binghamton, New York

## Project Details

### Data Acquisition

- Downloaded 200,000 rows of business data from Yelp, describing each business with various characteristics, including star rating, review count, business name, attributes, categories, and more. However, I could only use 10000 rows due to the lack of computational capability at my disposal
- The attribute section contains a dictionary listing characteristics such as "parking: yes" or "dress attire: formal."
- The category section is a string representing different business categories.

### Data Preprocessing

- Created a filtered dataframe to isolate businesses with the category "restaurant."
- Split the attributes section and created new columns for each attribute, resulting in a significant number of new columns with null values.
- Investigated the mean star rating for each attribute value and dealt with null values.
- Chose dress attire, catering, and noise level for further analysis due to significant changes in mean values and low null values.
- Filtered out rows with null values in the selected attributes.

### Model Creation

- Applied one-hot encoding to convert categorical values into numerical ones.
- Developed a simple linear model with a Mean Squared Error (MSE) of 0.48.
- Created a neural network model with a learning rate of 0.003, tanh activation function, and RMS optimizer, achieving a slightly improved MSE of 0.46.

### Model Evaluation

- Visualized models and observed that the predictions tend to fall in the range of 3-4 stars.
- Noted that the model struggles with extreme values, often predicting values in the 3-4 range, indicating slight underfitting.
- Despite limitations, the model provides a good estimate for a significant portion of businesses.

### Results Visualization

- The scatterplot demonstrates the model's tendency to overproject low-star restaurants and underproject high-star restaurants.
- The model consistently predicts values in the 3-4 range, indicating a safe approach but still offering a reasonable estimate.

# Email Sender Prediction Project

### Overview

This project aims to predict the sender of an email using email content. This is particularly important in scenarios where an emailer flagged for malicious activities attempts to use a different email address to continue their activities. By identifying the writing style and patterns of individuals, the model can predict if the same person is behind different email addresses.

### Approach

- The solution involves using the vectors acquired from word2vec to create a random forest model that predicts the 'from' values. The vectors were generated from the message column of the emails. The objective is for the model to recognize each individual's writing style and accurately determine the sender of a message based on its content.

### Results

- The model achieved an accuracy of 87%, demonstrating its effectiveness in predicting the sender based on email content.

### Methodology

1. **Data Preparation:**
   - Emails are preprocessed, and the message content is used to create word2vec vectors.
   - These vectors represent the unique writing style of each sender.

2. **Model Training:**
   - A random forest classifier is trained using the word2vec vectors to predict the 'from' values.
   - The model learns to identify patterns and styles unique to each sender.

3. **Evaluation:**
   - The model's performance is evaluated, achieving an accuracy of 87%.

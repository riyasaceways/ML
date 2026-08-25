[← Back to Index](../../../README.md) | [← Back](../)

---
# a. Data Collection

Data collection means gathering the information needed to train and build an ML model.

The data can come from sources such as databases, websites, sensors, applications, cameras, 
or user activity.

**Example:**
> For a house-price prediction model, we might collect data 
> about house size, location, number of rooms, and previous selling prices.

# b. Data Preparation

Raw data is usually not ready to be used directly by a machine learning model. Data preparation means 
cleaning and organizing the data.

This can include:

Removing incorrect or duplicate data
Handling missing values
Converting data into suitable formats
Selecting useful features

**Example:**
> If some houses have a missing value for the number of rooms, we need to handle that before training
> the model.

# c. Model Training

Model training is where the ML algorithm learns patterns from the prepared data.

We give the model training data and allow it to adjust its internal parameters so that it can make 
better predictions.

**Example:**
> We give the model many houses with their features and actual prices. The model learns the relationship 
> between those features and house prices.

# d. Model Evaluation

After training, we need to check how well the model performs on data it has not seen during training.

This helps us determine whether the model is making useful predictions or whether it has problems such
as overfitting.

**Example:**
> We test our house-price model using houses that were not included in its training data and compare its 
> predictions with the actual prices.

# e. Model Deployment

If the model performs well enough, it can be deployed so that it can be used in a real application.

Deployment means putting the trained model into an environment where it can receive new data and produce
predictions.

**Example:**
> A house-price prediction model could be integrated into a real-estate website so users can enter house
> details and receive an estimated price.

# f. Continuous Improvement of Models

An ML model is not necessarily finished after deployment. Real-world data and conditions can change 
over time.

The model may need to be monitored, evaluated, retrained with new data, or improved when its
performance decreases.

**Example:**
> House prices can change because of changes in the economy or the housing market. New house-price data
> can be collected and used to retrain the model.
---
[← Back to Index](../../../README.md) | [← Back](../)
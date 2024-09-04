## Instructions to Run the Project

1. **Data Preparation and Model Training**:
   - **Open the `model_training.ipynb` Jupyter Notebook** located in the `notebooks/` directory.
   - **Data Preparation**:
     - **Load Data**: Import the dataset from CSV files and perform initial exploration.
     - **Feature Engineering**: Extract and preprocess relevant features from the dataset, including date-time features such as hour, day of the week, and month.
     - **Sequence Creation**: Convert the dataset into sequences suitable for LSTM training. Sequences are created with a length of 24 hours, where each sequence includes multiple features (e.g., HUFL, HULL, MUFL, etc.) and the target variable (OT).
     - **Split Data**: Split the dataset into training and test subsets, ensuring the last 24 hours are reserved for testing to evaluate the model's performance.

2. **Model Building and Training**:
   - **Define LSTM Model**:
     - The model is built using TensorFlow/Keras with three LSTM layers, each followed by dropout and batch normalization to improve generalization.
     - The architecture includes a final dense layer to output the predicted oil temperature (OT).
   - **Training**:
     - Train the LSTM model using the prepared sequences from the training data.
     - The model learns to predict the oil temperature for the next hour based on past sequences of 24 hours.

3. **Model Evaluation and Visualization**:
   - **Generate Predictions**:
     - Use the trained LSTM model to predict oil temperature for the next 24 hours based on the test data.
     - The predictions are generated sequentially, iterating over the test data and updating the input sequences as predictions are made.
   - **Compare Predictions to Actual Values**:
     - The last 24 hours of the dataset are used as actual values to compare against the model's predictions.
     - **Visualize Results**:
       - Plot graphs to compare the predicted oil temperature with the actual values for the last 24 hours.
       - Visualize the results using Matplotlib to assess the model's performance visually.

## Model Training and Evaluation Summary

1. **Dataset Preparation**:
   - **Data Loading**: The dataset was loaded, and initial exploration was conducted to understand the structure and content.
   - **Feature Extraction**: Relevant features such as hour, day of the week, month, and other variables were extracted and scaled.
   - **Sequence Creation**: The data was transformed into sequences of 24 hours to be used for training the LSTM model. Each sequence included historical data for the features and the target variable (OT).

2. **LSTM Model Architecture**:
   - The model consists of three LSTM layers with 80, 60, and 50 units, respectively, each followed by dropout and batch normalization. A dense layer at the end provides the final prediction.

3. **Training and Prediction**:
   - The model was trained on historical sequences to forecast the oil temperature for the next 24 hours. Predictions were generated iteratively for each hour based on the previous hours' data.

4. **Visualization**:
   - Results were visualized by plotting the actual vs. predicted oil temperature values for the last 24 hours. This allowed for an intuitive assessment of the model's performance.
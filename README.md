# Flight-Prediction
Flight Price Predictor is a web application that uses machine learning to forecast airfare prices for domestic flights in India. Built with Flask and scikit-learn, this tool allows travelers to make more informed booking decisions by predicting ticket prices based on various flight parameters.

# Features
User-friendly Interface: Intuitive design with responsive elements
Real-time Predictions: Get instant fare estimates based on your input
Multiple Parameters: Consider various factors like airline, date, time, source, destination, and stops
Visually Appealing: Clean and modern UI with animations

# Technologies Used
Frontend: HTML, CSS, JavaScript, Bootstrap
Backend: Flask (Python)
Machine Learning: scikit-learn, pandas, numpy
Data Visualization: Matplotlib, Seaborn
Deployment: Render

# Dataset
The model is trained on the Flight Price Dataset from Kaggle, which includes features like:

| Feature                   | Description        
|---------------------------|--------------------------------------------------------  
| Airline                   | The airline company (e.g., IndiGo, Air India, SpiceJet) 
| Date of Journey           | Date of the flight 
| Source & Destination      | Departure and arrival cities 
| Route                     | Flight route information 
| Departure & Arrival time  | Time of departure and arrival 
| Duration                  | Total flight duration 
| Total Stops               | Number of stops between source and destination 
| Additional Info           | Additional information about the flight 
| Price                     | Target variable (fare in INR) 

# Machine Learning Model
The prediction system implements Random Forest Regression with the following performance metrics:

R² Score: 0.81
RMSE: 2738.43
MAE: 1684.87

# Model Comparison

| Model                     | R² Score  | RMSE    | MAE 
|---------------------------|-----------|---------|---------
| Linear Regression         | 0.62      | 3792.56 | 2998.33 
| Support Vector Regression | 0.64      | 3703.22 | 2588.24 
| Random Forest             | 0.81      | 2738.43 | 1684.87
| Decision Tree             | 0.74      | 3163.12 | 2154.37 

# Installation and Setup
1. Clone the repository
git clone https://github.com/Aviya-Singh/Flight-Prediction.git
cd Flight-Prediction

2. Create and activate virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

3. Install dependencies
pip install -r requirements.txt

4. Run the application
python app.py

5. Visit the application in your browser
http://localhost:5000

# Model Training Process

1. Data Cleaning
Handling missing values
Removing outliers
Converting data types
Standardizing date and time formats

2. Feature Engineering
Creating new features: journey day, month, flight duration in hours
Extracting time period of day (morning, afternoon, evening, night)
Creating price per kilometer feature

3. Categorical Encoding
One-hot encoding for airlines
Label encoding for source/destination cities

4. Model Selection
Evaluating various regression models
Cross-validation for robust performance assessment

5. Hyperparameter Tuning
Using GridSearchCV to optimize model parameters like:

n_estimators: 100
max_depth: 20
min_samples_split: 2
min_samples_leaf: 2

5. Model Persistence
Saving the best model using pickle for production deployment

# API Endpoints
| Endpoint      | Method                         | Description                                       |
|---------------|--------------------------------|---------------------------------------------------|
| `/` | GET     | Home page with prediction form |
| `/predict`    | POST                           | Returns fare prediction based on input parameters |
| `/statistics` | GET                            | Shows model performance statistics                |

# License
This project is licensed under the MIT License - see the LICENSE file for details.
Contact: Aviya Singh 
Project Link: https://github.com/Aviya-Singh/Flight-Prediction

# References
1. Korkmaz, Huseyin. (2024). Prediction of Airline Ticket Price Using Machine Learning Method. Journal of Transportation and Logistics. 9. 1-14. 10.26650/JTL.2024.1486696. 
2. M. Tuli, L. Singh, S. Tripathi and N. Malik, "Prediction of Flight Fares Using Machine Learning," 2023 13th International Conference on Cloud Computing, Data Science & Engineering (Confluence), Noida, India, 2023, pp. 13-18, doi: 10.1109/Confluence56041.2023.10048801.
3. Gupta, Shikha & Gupta, Nishi & Publication Hub, Tjcse. (2024). Flight Fare Prediction Using Machine Learning. 

# Acknowledgements
Kaggle for the dataset
scikit-learn for machine learning tools
Flask for the web framework
Bootstrap for frontend components

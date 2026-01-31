# House Price Prediction

A machine learning web application that predicts house prices in Bengaluru based on location, BHK (bedrooms), bathrooms, and square footage.

## Project Overview

This project combines data science and web development to create an end-to-end house price prediction system. It uses a Ridge Regression model trained on Bengaluru housing data to provide real-time price predictions through an interactive web interface.

## Features

- **Data Preprocessing**: Comprehensive data cleaning and handling of missing values
- **Machine Learning Model**: Ridge Regression model trained on historical house price data
- **Web Interface**: User-friendly Flask web application with Bootstrap styling
- **Real-time Predictions**: Instant price predictions based on user inputs
- **Location Support**: Predictions for multiple locations in Bengaluru

## Project Structure

```
House-price-prediction/
├── README.md                          # Project documentation
├── House_price_prediction.ipynb       # Data preprocessing & model training notebook
├── main.py                            # Flask web application
├── Bengaluru_House_Data.csv          # Original dataset
├── Cleaned_data.csv                   # Preprocessed dataset
├── RidgeModel.pkl                     # Trained Ridge Regression model
├── templates/
│   └── index.html                     # Web interface HTML template
└── .git/                              # Git version control
```

## Dataset

**Source**: Bengaluru_House_Data.csv

**Features Used**:
- `location`: Area/locality in Bengaluru
- `total_sqft`: Total area in square feet
- `bath`: Number of bathrooms
- `bhk`: Number of bedrooms (BHK)
- `price`: House price (target variable)

**Data Preprocessing Steps**:
1. Removed irrelevant columns: `availability`, `society`, `area_type`, `balcony`
2. Handled missing values:
   - `location`: Filled with 'Sarjapur Road'
   - `size` (BHK): Filled with '2 BHK'
3. Extracted BHK from the `size` column
4. Removed duplicates
5. Standardized and cleaned the data

## Model

**Algorithm**: Ridge Regression

The model is trained to predict house prices (in hundreds of thousands of rupees) based on:
- Location
- Total square footage
- Number of bathrooms
- Number of bedrooms (BHK)

The trained model is serialized as `RidgeModel.pkl` using Python's pickle module.

## Installation & Setup

### Prerequisites
- Python 3.7+
- pip or conda

### Required Packages
```
pandas
numpy
flask
scikit-learn
pickle
```

### Installation Steps

1. Clone the repository:
```bash
git clone https://github.com/LAKHANATOLIYA/House-price-prediction.git
cd House-price-prediction
```

2. Install dependencies:
```bash
pip install pandas numpy flask scikit-learn
```

3. Ensure the model and data files are in the project directory:
   - `RidgeModel.pkl` (trained model)
   - `Cleaned_data.csv` (preprocessed data)

## Usage

### Running the Web Application

1. Navigate to the project directory:
```bash
cd House-price-prediction
```

2. Run the Flask application:
```bash
python main.py
```

3. Open your browser and visit:
```
http://localhost:5001
```

4. Use the form to enter:
   - **Location**: Select from dropdown
   - **BHK**: Number of bedrooms
   - **Bathrooms**: Number of bathrooms
   - **Square Feet**: Total area in square feet

5. Click "Predict Price" to see the estimated house price

### Example Prediction
- Location: Sarjapur Road
- BHK: 3
- Bathrooms: 2
- Square Feet: 1500
- **Predicted Price**: ₹50,00,000 (example output)

## Model Training

The notebook `House_price_prediction.ipynb` contains:
- Data loading and exploration
- Exploratory Data Analysis (EDA)
- Feature engineering
- Data cleaning and preprocessing
- Ridge Regression model training
- Model evaluation

To retrain the model:
1. Open `House_price_prediction.ipynb` in Jupyter
2. Run all cells
3. The updated `RidgeModel.pkl` will be saved

## Technical Stack

- **Backend**: Flask (Python web framework)
- **Frontend**: HTML + Bootstrap CSS
- **Machine Learning**: scikit-learn
- **Data Processing**: pandas, numpy
- **Model Serialization**: pickle

## API Endpoints

### GET `/`
- Returns the home page with location dropdown
- **Response**: HTML form with list of locations

### POST `/predict`
- Predicts house price based on input features
- **Parameters**:
  - `location` (string): Selected location
  - `bhk` (float): Number of bedrooms
  - `bath` (float): Number of bathrooms
  - `total_sqft` (string): Total square footage
- **Response**: Predicted price in rupees

## Performance

The Ridge Regression model provides:
- Fast inference time (< 100ms)
- Regularization to prevent overfitting
- Stable predictions across different input ranges

## Future Enhancements

- Add more features (age of property, nearby amenities, etc.)
- Implement multiple algorithms and model comparison
- Add data visualization and statistics
- Deploy on cloud platforms (Heroku, AWS, GCP)
- Add user authentication and history tracking
- Implement API with documentation (Swagger/OpenAPI)
- Add more Bengaluru locations to the dataset

## Author

**LAKHANATOLIYA**
- Email: latoliya334@gmail.com
- GitHub: https://github.com/LAKHANATOLIYA/House-price-prediction

## License

This project is open source and available under the MIT License.

## Acknowledgments

- Bengaluru housing dataset for providing real-world data
- Flask framework documentation
- scikit-learn for machine learning algorithms

## Contact & Support

For issues, suggestions, or improvements, feel free to:
- Open an issue on GitHub
- Contact via email: latoliya334@gmail.com

---

**Last Updated**: January 31, 2026

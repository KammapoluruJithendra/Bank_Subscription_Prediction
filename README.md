# Bank Prediction Algorithm API

This repository contains the implementation of a Flask-based web application for predicting bank-related outcomes using a pre-trained machine learning model.

## Files

### 1. `app.py`
This is the main file for the Flask application. It sets up the routes and handles the prediction logic using a pre-trained model.

Key components:
- **Dependencies**: 
  - `pickle` for loading the pre-trained model
  - `Flask` for setting up the web application and handling requests
  - `numpy` and `pandas` for data manipulation

- **Routes**:
  - `/` : Renders the home page (`home.html`)
  - `/predict_api` : API endpoint for making predictions. Accepts JSON data and returns a prediction.
  - `/predict` : Endpoint for making predictions via form submission on the web page. Returns the prediction result on the home page.

### 2. `bank_algorithm.pkl`
This is the pre-trained machine learning model used for making predictions. The model is loaded using `pickle` and used within the Flask application to generate predictions.

## Usage

### Running the Application
1. Ensure you have Python installed on your system.
2. Install the required packages:
   ```sh
   pip install flask numpy pandas
   ```
3. Place the `bank_algorithm.pkl` file in the `Model` directory.
4. Run the Flask application:
   ```sh
   python app.py
   ```
5. Navigate to `http://127.0.0.1:5000/` in your web browser to access the home page.

### API Usage
- **Prediction API**: Send a POST request to `/predict_api` with JSON data containing the features. The API will return the prediction result in JSON format.

Example request:
```json
{
  "data": {
    "feature1": value1,
    "feature2": value2,
    ...
  }
}
```

Example response:
```json
{
  "prediction": "Yes" or "No"
}
```

## Project Structure
```
.
├── Model
│   └── bank_algorithm.pkl
├── app.py
└── templates
    └── home.html
```

- `Model/bank_algorithm.pkl`: Directory containing the pre-trained model.
- `app.py`: Main Flask application file.
- `templates/home.html`: HTML template for the home page.

## Author
Jithendra

## Acknowledgments
- This project uses a pre-trained model which should be attributed accordingly if sourced externally.
- Flask documentation and tutorials for web application development.

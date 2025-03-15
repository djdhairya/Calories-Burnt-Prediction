# Calories Burnt Prediction

## Overview
This project predicts the number of calories burned during exercise based on multiple physiological parameters such as age, height, weight, duration, heart rate, and body temperature. The application is built using FastAPI and a machine learning model trained with XGBoost.

## Features
- **Web Interface**: Users can enter their details via an HTML form.
- **FastAPI Backend**: Processes user input and returns predicted calorie values.
- **Machine Learning Model**: A trained pipeline using XGBoost for calorie prediction.
- **Data Preprocessing**: StandardScaler and OrdinalEncoder are used for feature transformation.

## Installation
### Prerequisites
Ensure you have the following installed:
- Python 3.8+
- FastAPI
- Uvicorn
- Pandas
- Scikit-learn
- XGBoost
- Matplotlib
- Seaborn
- Jinja2

### Steps
1. Clone the repository:
   ```sh
   git clone https://github.com/djdhairya/Calories-Burnt-Prediction.git
   
   ```
2. Install dependencies:
   ```sh
   pip install -r requirements.txt
   ```
3. Run the FastAPI server:
   ```sh
   uvicorn app:app --reload
   ```
4. Open your browser and visit `http://127.0.0.1:8000/`.

## File Structure
```
├── data/
│   ├── calories.csv
│   ├── exercise.csv
├── model/
│   ├── pipeline_model.pkl
├── templates/
│   ├── index.html
│   ├── result.html
├── burnt_predict.ipynb
├── app.py
├── README.md
```

## Data Processing & Model Training
- The dataset combines `calories.csv` and `exercise.csv` using `User_ID`.
- Preprocessing includes handling missing values, encoding categorical features, and standardizing numerical features.
- The model is trained using XGBoost with a cross-validation approach (K-Fold with 5 splits).
- The final trained model is saved as `pipeline_model.pkl`.

## API Endpoints
### Home Page
- `GET /`
  - Displays the web form for user input.

### Prediction Endpoint
- `POST /predict`
  - Accepts form data and returns the predicted calorie expenditure.

## Web Interface
- **index.html**: Input form for user data submission.
- **result.html**: Displays predicted calories burnt.
- Uses Tailwind CSS for styling.

## Results & Evaluation
- Model performance is evaluated using:
  - **R² Score**: Measures model accuracy.
  - **Mean Absolute Error (MAE)**: Evaluates prediction error.
  - **Cross-Validation**: Ensures robustness with K-Fold validation.

## Visualization
The dataset and model performance are visualized using Matplotlib and Seaborn:
- **Gender Distribution**
  ```python
  sns.countplot(data['Gender'])
  plt.show()
  ```
- **Age Distribution**
  ```python
  sns.distplot(data['Age'])
  plt.show()
  ```
- **Height & Weight Distribution**
  ```python
  sns.distplot(data['Height'])
  sns.distplot(data['Weight'])
  plt.show()
  ```
- **Prediction vs Actual Calories Burnt**
  ```python
  plt.scatter(y_test, y_pred)
  plt.xlabel("Actual Calories")
  plt.ylabel("Predicted Calories")
  plt.title("Actual vs Predicted Calories Burnt")
  plt.show()
  ```

## Future Enhancements
- Add more physiological parameters for improved accuracy.
- Deploy as a web app using cloud platforms like AWS/GCP.
- Improve UI with interactive visualizations.

## License
This project is licensed under the MIT License.


![Screenshot 2025-03-15 121352](https://github.com/user-attachments/assets/bbab2bbe-fb17-4ab4-a771-44ce259d0595)
![Screenshot 2025-03-15 121505](https://github.com/user-attachments/assets/e0f6e5fc-98c9-411c-91be-38b0d982ad35)
![Screenshot 2025-03-15 121511](https://github.com/user-attachments/assets/3cab3680-54f2-4dbe-b4a2-6d3a709066f5)





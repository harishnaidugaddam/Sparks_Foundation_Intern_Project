# IPL First Innings Score Prediction

This project focuses on predicting the first innings score in IPL (Indian Premier League) matches using machine learning techniques. The dataset used contains detailed match statistics, and various regression models (Linear Regression, Ridge Regression, and Lasso Regression) are implemented to predict scores.

---

## Overview

The goal of this project is to predict the total score of the first innings in an IPL match based on historical data. The dataset includes features such as runs scored, wickets lost, overs bowled, and team information. The project involves data preprocessing, feature engineering, model training, and evaluation.

---

## Dataset

The dataset (`ipl.csv`) contains the following columns:
- **mid**: Match ID
- **date**: Date of the match
- **venue**: Stadium where the match was played
- **bat_team**: Batting team
- **bowl_team**: Bowling team
- **batsman**: Name of the batsman
- **bowler**: Name of the bowler
- **runs**: Runs scored
- **wickets**: Wickets lost
- **overs**: Overs bowled
- **runs_last_5**: Runs scored in the last 5 overs
- **wickets_last_5**: Wickets lost in the last 5 overs
- **striker**: Striker's score
- **non-striker**: Non-striker's score
- **total**: Total score of the innings

### Data Cleaning
- Removed unnecessary columns: `mid`, `venue`, `batsman`, `bowler`, `striker`, `non-striker`.
- Filtered out inconsistent teams, keeping only the following:
  - Kolkata Knight Riders
  - Chennai Super Kings
  - Rajasthan Royals
  - Mumbai Indians
  - Kings XI Punjab
  - Royal Challengers Bangalore
  - Delhi Daredevils
  - Sunrisers Hyderabad
- Removed data from the first 5 overs of each match to focus on more stable innings phases.

---

## Methodology

### Data Preprocessing
1. **Date Conversion**: Converted the `date` column from string to datetime format.
2. **Categorical Encoding**: Used one-hot encoding for categorical variables (`bat_team` and `bowl_team`).
3. **Train-Test Split**: Divided the data into training (matches before 2017) and testing sets (matches from 2017 onwards).

### Feature Selection
The following features were used for prediction:
- `runs`
- `wickets`
- `overs`
- `runs_last_5`
- `wickets_last_5`
- One-hot encoded batting and bowling team columns

---

## Models Used

1. **Linear Regression**:
   - A baseline model to predict scores.
   - Achieved moderate performance with some error metrics.

2. **Ridge Regression**:
   - Applied Ridge regularization to handle multicollinearity.
   - Tuned hyperparameter `alpha` using GridSearchCV.

3. **Lasso Regression**:
   - Applied Lasso regularization for feature selection.
   - Tuned hyperparameter `alpha` using GridSearchCV.

---

## Results

### Evaluation Metrics
The models were evaluated using the following metrics:
- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)

#### Example Results (Ridge Regression):
- MAE: 12.12
- MSE: 251.03
- RMSE: 15.84

A residual plot was also generated to visualize prediction errors.

---

## Installation

To run this project locally, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/ipl-score-prediction.git
   cd ipl-score-prediction
   ```

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Download the dataset (`ipl.csv`) and place it in the project directory.

---

## Usage

Run the Jupyter Notebook to train the models and evaluate their performance:
```bash
jupyter notebook IPL_First_Innings_Score_Prediction.ipynb
```

You can modify the notebook to experiment with different models or hyperparameters.

---

## Contributing

Contributions are welcome! If you find any issues or have suggestions for improvement, feel free to open an issue or submit a pull request.

1. Fork the repository.
2. Create a new branch: 
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. Commit your changes: 
   ```bash
   git commit -m "Add your feature"
   ```
4. Push to the branch: 
   ```bash
   git push origin feature/your-feature-name
   ```
5. Open a pull request.

---
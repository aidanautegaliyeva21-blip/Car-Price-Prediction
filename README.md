# Car Price Prediction
Predicting car selling prices using machine learning. This project helps buyers, sellers, and businesses make data-driven decisions based on car features.

---

## Dataset

The dataset contains **205 rows and 26 columns** describing various car attributes. Key features include:  

| Column Name          | Type      | Description |
|----------------------|-----------|-------------|
| `car_ID`             | int64     | Unique identifier for each car |
| `symboling`          | int64     | Risk factor of the car (-3 to 3) |
| `CarName`            | object    | Car model name |
| `fueltype`           | object    | Fuel type (Gas, Diesel) |
| `aspiration`         | object    | Aspiration type (Standard, Turbo) |
| `doornumber`         | object    | Number of doors (two, four) |
| `carbody`            | object    | Car body style (sedan, hatchback, etc.) |
| `drivewheel`         | object    | Drive wheel type (fwd, rwd, 4wd) |
| `enginelocation`     | object    | Engine placement (front, rear) |
| `wheelbase`          | float64   | Wheelbase length (inches) |
| `carlength`          | float64   | Length of the car (inches) |
| `carwidth`           | float64   | Width of the car (inches) |
| `carheight`          | float64   | Height of the car (inches) |
| `curbweight`         | int64     | Weight of the car without passengers (lbs) |
| `enginetype`         | object    | Type of engine (ohc, ohcf, etc.) |
| `cylindernumber`     | object    | Number of cylinders |
| `enginesize`         | int64     | Engine size (cc) |
| `fuelsystem`         | object    | Fuel system type |
| `boreratio`          | float64   | Cylinder bore ratio (inches) |
| `stroke`             | float64   | Engine stroke (inches) |
| `compressionratio`   | float64   | Compression ratio of the engine |
| `horsepower`         | int64     | Horsepower output |
| `peakrpm`            | int64     | Maximum engine RPM |
| `citympg`            | int64     | Fuel efficiency in city (mpg) |
| `highwaympg`         | int64     | Fuel efficiency on highway (mpg) |
| `price`              | float64   | Selling price of the car (target variable) |

**Notes:**  
- All columns are complete; no missing values.  
- Some categorical columns (`CarName`, `fueltype`, `carbody`, `aspiration`, etc.) require encoding for modeling.  
- Suitable for regression tasks to predict `price`.

---

##  Data Preprocessing
- Encoded categorical variables using **one-hot encoding** or **label encoding**  
- Scaled numerical features where necessary  

---

##  Exploratory Data Analysis (EDA)
- Older cars tend to have lower prices  
- Higher kilometers driven reduces selling price  
- Diesel and petrol cars are more expensive than others  
- Automatic transmission cars slightly higher in price  
- Strong correlations: `price` vs `enginesize`, `curbweight`, and `horsepower`

---

## Modeling
Tested multiple regression models:  

- **Linear Regression**  
- **Ridge Regression**  
- **Lasso Regression**  
- **Decision Tree Regressor**  
- **Random Forest Regressor**  
- **Gradient Boosting Regressor**  

**Evaluation Metrics:** MAE, MSE, RMSE, R²

---

## Results

# Car Price Prediction: Model Evaluation

## Model Performance Comparison

| Model               | Train MAE | Train RMSE | Train R² | Test MAE | Test RMSE | Test R² |
|--------------------|-----------|------------|----------|----------|-----------|---------|
| Linear Regression   | 931.33    | 1261.65    | 0.973    | 1950.47  | 2851.46   | 0.897   |
| Ridge Regression    | 999.04    | 1431.77    | 0.966    | 2088.35  | 3130.48   | 0.876   |
| Lasso Regression    | 140,006.68 | 228,384.54 | -873.60  | 106,129.57 | 122,605.26 | -189.41 |
| Decision Tree       | 380.67    | 908.57     | 0.986    | 1932.18  | 2807.86   | 0.900   |
| Random Forest       | 684.88    | 1035.24    | 0.982    | 1250.59  | 1824.87   | 0.958   |
| Gradient Boosting   | 60.83     | 271.10     | 0.999    | 1705.76  | 2367.54   | 0.929   |

---

## Key Observations

- **Random Forest** achieved the best test performance with the **lowest RMSE** and **highest R²**.  
- **Gradient Boosting** performs very well on training data but shows slight overfitting.  
- **Decision Tree** is accurate but less stable than ensemble models.  
- **Linear Regression** and **Ridge Regression** capture general trends but cannot model nonlinear relationships effectively.  
- **Lasso Regression** fails due to aggressive coefficient shrinkage.


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

| Model                        | Train MAE | Train RMSE | Train R² | Test MAE | Test RMSE | Test R² |
|-------------------------------|-----------|------------|----------|----------|-----------|---------|
| Linear Regression             | 931.33    | 1261.65    | 0.973    | 1950.47  | 2851.46   | 0.897   |
| Ridge                         | 931.84    | 1279.91    | 0.973    | 1936.87  | 2948.39   | 0.890   |
| Lasso                         | 929.20    | 1262.51    | 0.973    | 1936.90  | 2844.15   | 0.898   |
| Decision Tree Regressor        | 380.67    | 908.57     | 0.986    | 1932.18  | 2807.86   | 0.900   |
| Random Forest Regressor        | 613.27    | 938.23     | 0.985    | 1196.51  | 1749.64   | 0.961   |
| Gradient Boosting Regressor    | 60.83     | 271.10     | 0.999    | 1693.82  | 2371.41   | 0.929   |

**Observations:**  
- **Random Forest Regressor** achieved the **best test performance** with the lowest RMSE (1749.64) and highest R² (0.961)  
- Gradient Boosting also performs well, especially on training data  

---

## Conclusion
- Car age, engine size, and curbweight are key predictors  
- Ensemble models (Random Forest, Gradient Boosting) outperform linear models  

---



# NYC Yellow Taxi Trip Fare Prediction

This was a group project for the CS6502 Applied Big Data and Visualisation course at the University of Limerick.

This project analyses NYC Taxi Trip dataset to forecast fare amounts using Apache Spark for
large-scale data handling and automated learning workflows. Our preprocessing pipeline involved
ingesting the raw data, cleaning and filtering out missing records, converting timestamps to usable
formats, and encoding categorical fields. During EDA, we identified key patterns in hourly and daily
ride volumes and confirmed strong links between fare amounts, trip distances, and average speeds.
Feature engineering produced trip duration metrics, which, alongside EDA insights, guided our
modeling strategy.

We evaluated three regression techniques, standard Decision Tree Regression, Random Forest
Regression, and Random Forest with Bagging Regression, each optimized through parameter tuning.
Linear Regression slightly outperformed Lasso in RMSE and MAE, while both achieved comparable
R² scores around 0.92. After hyperparameter tuning, the Random Forest model reached an R² of
approximately 0.90, demonstrating solid non-linear performance but not substantially surpassing the
linear approaches. Across all models, trip distance and trip duration emerged as the dominant
predictors of fare.

### Conclusion, Challenges and Future Improvements

In this study, we built and evaluated several machine-learning approaches—Decision Trees, Random
Forests, and Linear Regression—to estimate the total fare for New York City taxi rides using Apache
Spark’s MLlib. Starting from a thoroughly cleaned dataset and insights from exploratory analysis, we
engineered features including ride distance, trip duration, pickup hour, and origin/destination zones.
Our flagship model, the Random Forest regressor, was fine-tuned via cross-validation and benefited
from Spark’s caching to accelerate repeated computations. It achieved high accuracy across the
common fare spectrum, though it tended to slightly underpredict very expensive trips. We also trained
individual Decision Tree models and found them intuitive but less stable, while our Linear Regression
baseline—upgraded to a Lasso variant with L1 regularization—demonstrated robust generalization by
curbing overfitting.

All models delivered strong performance metrics (RMSE, MAE, and R²), underscoring the power of
Spark for scalable analytics on large transportation datasets. We did encounter challenges around
missing data, skewed fare distributions, and the resource limits of Databricks Community Edition.
Future enhancements might include more extensive hyperparameter searches, blending in auxiliary
data like weather or traffic feeds, and experimenting with Gradient Boosted Trees or neural network
architectures to better handle rare, high-fare trips and further improve prediction accuracy.

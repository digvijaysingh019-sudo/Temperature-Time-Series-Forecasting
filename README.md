# Temperature-Time-Series-Forecasting
Project Summary
This project addresses the challenge of forecasting temperature data by identifying and leveraging the inherent cyclical nature of time. While raw temporal data often confuses machine learning models due to its discontinuous nature, we transformed it into a continuous mathematical format using trigonometric functions.

Technical Methodology
Data Manipulation (pandas): Used for loading datasets, handling missing values, and executing noise reduction via a 30-day moving average to reveal underlying trends.

Cyclic Feature Engineering (numpy): * The Problem: Raw month integers (1-12) create a false sense of distance between December (12) and January (1).

The Solution: We mapped months onto a 2D Unit Circle using Sine and Cosine transformations.

Logic: By using both sin and cos coordinates, we ensured every month has a unique, continuous position, allowing the model to understand the smooth transition of seasons.

Predictive Modeling (scikit-learn): * Implemented LinearRegression to capture the relationship between cyclical seasonal features and temperature.

Temporal Splitting: Unlike standard random splitting, we performed a chronological split (Training: 1981-1989; Testing: 1990-1991) to eliminate Data Leakage and simulate real-world forecasting.

Visualization (matplotlib & seaborn): Used to perform diagnostic residual analysis, confirming that the model errors follow a Normal Distribution, indicating high model reliability.

Key Outcomes
Improved Correlation: Cyclic encoding significantly boosted feature correlation with the target variable compared to raw numerical inputs.

Performance: Achieved a Mean Squared Error (MSE) of 6.85, demonstrating that feature engineering is often more impactful than model complexity.

Reliability: The residual analysis confirms an unbiased model capable of effectively predicting temperature trends.

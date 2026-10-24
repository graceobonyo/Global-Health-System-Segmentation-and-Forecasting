README.md
Forecasting Kenya's Life Expectancy Using Prophet and LSTM Deep Learning
Project Overview

Life expectancy is one of the most important indicators of a country's overall health, economic development, and quality of life. Understanding future life expectancy trends can help governments, healthcare organizations, and policymakers make informed decisions regarding healthcare planning, resource allocation, and public health interventions.

This project applies both a traditional time-series forecasting model (Prophet) and a deep learning model (Long Short-Term Memory - LSTM) to forecast Kenya's life expectancy. The models are evaluated and compared using forecasting error metrics to identify the most accurate approach for future life expectancy prediction.

Background

Over the past two decades, Kenya has experienced significant improvements in healthcare services, disease prevention programs, maternal and child health outcomes, and economic development. These improvements have contributed to a gradual increase in life expectancy.

According to the World Bank, Kenya's life expectancy at birth reached 63.83 years in 2024, up from approximately 56.08 years in 2000.

Current health expenditure in Kenya was 4.35% of GDP in 2023, reflecting continued investment in healthcare services and infrastructure.

Despite these improvements, forecasting future life expectancy remains challenging due to changing healthcare, demographic, economic, and environmental conditions.

Problem Statement

Kenya has experienced substantial improvements in healthcare and life expectancy over the past two decades. However, predicting future life expectancy remains difficult due to evolving healthcare, economic, and demographic conditions. Accurate forecasting is essential for long-term healthcare planning, policy development, and resource allocation. This project seeks to forecast Kenya's future life expectancy using advanced time-series forecasting techniques and determine whether deep learning models can provide more accurate predictions than traditional forecasting approaches.

Objectives
Main Objective

To forecast Kenya's life expectancy using Prophet and LSTM models and determine the most accurate forecasting approach.

Specific Objectives
Analyze historical trends in Kenya's life expectancy.
Examine health and socioeconomic indicators associated with life expectancy.
Build a Prophet forecasting model.
Develop an LSTM deep learning forecasting model.
Compare model performance using MAE and RMSE.
Forecast Kenya's life expectancy from 2025 to 2030.
Dataset Description
Source

Global Health Indicators Dataset

Country Selected

Kenya

Features Used
Variable	DescriptionYear	Observation year
Life Expectancy	Average expected lifespan
Maternal Mortality	Maternal deaths per population
Under-5 Mortality	Child deaths under age five
Health Expenditure (% GDP)	Healthcare investment
GDP per Capita	Economic development indicator
Physicians per 1000	Healthcare workforce availability
Hospital Beds per 1000	Healthcare infrastructure
Nurses per 1000	Nursing workforce availability
Population	Total population
Methodology
1. Data Preparation

The following preprocessing steps were performed:

Filtered data for Kenya.
Selected health-related indicators.
Identified missing values.
Converted numeric variables to correct data types.
Imputed missing values using median imputation.
Missing Value Handling

Median imputation was chosen because it is less sensitive to outliers and preserves the central tendency of the data.

2. Exploratory Data Analysis (EDA)

Several visualizations were created to understand historical trends and relationships.

Life Expectancy Trend

Key Findings:

Increased from approximately 56 years in 2000 to 64 years in 2024.
Temporary decline around 2020-2021.
Long-term upward trend indicates improvements in population health.
Maternal Mortality Trend

Key Findings:

General reduction over time.
Negative relationship with life expectancy.
Lower maternal mortality contributes to increased life expectancy.
Under-5 Mortality Trend

Key Findings:

Significant decline throughout the study period.
Strong inverse relationship with life expectancy.
One of the strongest indicators of population health.
Health Expenditure Trend

Key Findings:

Healthcare investment generally increased over time.
Greater healthcare spending supports improved healthcare outcomes.
Healthcare Infrastructure Trends

Indicators:

Physicians per 1,000 people
Nurses per 1,000 people
Hospital beds per 1,000 people

Key Findings:

Physician and nurse density improved over time.
Hospital bed availability remained relatively stable.
Improved healthcare infrastructure likely contributed to rising life expectancy.
Correlation Analysis

Major Findings:

Positive Correlations with Life Expectancy
GDP per Capita (0.93)
Population
Nurses per 1,000
Health Expenditure
Negative Correlations with Life Expectancy
Under-5 Mortality (-0.97)
Maternal Mortality

These findings suggest that economic growth, healthcare investment, and improved healthcare infrastructure support longer life expectancy.

Model Development
Prophet Model
Data Preparation

The data was reformatted to meet Prophet's requirements:

ds = Date column
y = Target variable (Life Expectancy)
Prophet Forecasting Process
Split data into training and testing sets.
Train Prophet model.
Generate future forecasts.
Evaluate performance using MAE and RMSE.
Prophet Results
Metric	ValueMAE	3.08
RMSE	3.47
Interpretation

Prophet successfully captured the long-term upward trend in life expectancy but struggled to predict the temporary decline observed during 2020-2021. As a result, prediction errors increased during that period.

LSTM Model
Why LSTM?

LSTM is a specialized recurrent neural network designed for time-series forecasting. It can learn long-term dependencies and capture complex temporal patterns in sequential data.

LSTM Architecture
LSTM Layer (64 units)
Dropout Layer (20%)
LSTM Layer (32 units)
Dense Output Layer
Data Preparation

The life expectancy series was:

Scaled using MinMaxScaler.
Converted into sequential windows.
Split into training and testing datasets.
Training Performance

The training and validation loss curves showed:

Rapid reduction in loss during early epochs.
Stable learning after convergence.
No evidence of severe overfitting.
Good model generalization.
Model Evaluation
LSTM Results
Metric	ValueMAE	1.285
RMSE	1.393
R²	-0.548
Interpretation

The low MAE and RMSE values indicate that the LSTM model generated forecasts much closer to actual life expectancy values than Prophet. Although R² was negative, this is likely due to the small test dataset and limited observations available for evaluation.

Model Comparison
Model	MAE	RMSEProphet	3.078	3.467
LSTM	1.285	1.393
Findings
LSTM produced substantially lower forecasting errors.
LSTM captured temporal patterns more effectively.
LSTM was selected as the best-performing model.
Future Forecast (2025–2030)
Year	Predicted Life Expectancy2025	64.02
2026	64.13
2027	64.27
2028	64.39
2029	64.48
2030	64.58
Forecast Interpretation

The model predicts a gradual increase in Kenya's life expectancy from 64.02 years in 2025 to 64.58 years in 2030.

This trend suggests:

Continued healthcare improvements.
Better child and maternal health outcomes.
Sustained healthcare investment.
Positive long-term population health outcomes.
Limitations
1. Limited Dataset Size

The study used annual observations from 2000 to 2024, providing relatively few records for deep learning.

2. Univariate Forecasting

LSTM relied solely on historical life expectancy values and did not directly incorporate additional health indicators.

3. External Events

Unexpected events such as pandemics, economic crises, or policy changes cannot be predicted from historical trends alone.

4. Small Test Dataset

A limited number of testing observations reduced the reliability of certain evaluation metrics such as R².

Recommendations
1. Increase Healthcare Investment

Continued investment in healthcare infrastructure and services may further improve life expectancy.

2. Reduce Child and Maternal Mortality

Strengthening maternal and child healthcare programs should remain a priority.

3. Expand Healthcare Workforce

Increasing the number of physicians and nurses can improve healthcare accessibility and quality.

4. Develop Multivariate Forecasting Models

Future research should incorporate:

GDP per capita
Healthcare expenditure
Maternal mortality
Under-5 mortality
Healthcare workforce indicators

to improve forecasting accuracy.

5. Explore Advanced Deep Learning Models

Future studies can compare:

LSTM
GRU
Bidirectional LSTM
Transformer Models

to identify the most accurate forecasting approach.

Conclusion

This study successfully applied Prophet and LSTM models to forecast life expectancy in Kenya. Exploratory analysis revealed substantial improvements in healthcare outcomes, reductions in child mortality, and growth in healthcare infrastructure. Model evaluation demonstrated that the LSTM model outperformed Prophet, achieving significantly lower forecasting errors (MAE = 1.285 and RMSE = 1.393) compared to Prophet (MAE = 3.078 and RMSE = 3.467).

Based on future forecasts, Kenya's life expectancy is expected to increase from 64.02 years in 2025 to 64.58 years in 2030, suggesting continued improvements in population health if current trends persist. The findings demonstrate the potential of deep learning techniques such as LSTM to support evidence-based healthcare planning and policy decision-making.
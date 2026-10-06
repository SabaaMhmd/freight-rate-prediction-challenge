# Spotter Machine Learning Assessment - Freight Rate Prediction



This repository contains the machine learning pipeline and solution for the Spotter Freight Rate Prediction assessment. The goal of this project is to accurately predict freight load rates (`posted\_rate`) using historical shipping data.



\## 📊 Approach \& Methodology



1\. \*\*Data Cleaning \& Preprocessing:\*\*

&#x20;  - \*\*Weights:\*\* Handled negative weights by taking the absolute value (`.abs()`) and imputed missing values using the median.

&#x20;  - \*\*Market Index \& Signals:\*\* Filled missing numerical features with their respective median values from the training set.

&#x20;  - \*\*Temporal Features:\*\* Extracted `month`, `dayofweek`, and `dayofyear` from timestamps to capture seasonal and weekly trends.



2\. \*\*Model Selection:\*\*

&#x20;  - Utilized \*\*`HistGradientBoostingRegressor`\*\* from Scikit-Learn. It is robust, handles missing values natively, and performs exceptionally well on tabular regression tasks.



3\. \*\*Validation \& Scoring:\*\*

&#x20;  - Performed local train/test splits for model evaluation (achieving a solid Validation MAE of \~140.01).

&#x20;  - Generated final predictions for 12,000 loads in `validation\_predictions.csv` and verified 100% compliance using the official company scorer script (`score.py`).

&#x20;  - Predicted December rates for the fixed route (Lexington to Fort Wayne) and generated the required chart (`candidate\_december.png`).



\---



\## 📂 Repository Structure



\- `freight\_rate\_prediction\_pipeline.ipynb`: The complete end-to-end Jupyter Notebook (Data Cleaning, Training, Validation, and Prediction).

\- `validation\_predictions.csv`: Final generated predictions for the validation dataset.

\- `december-chart-inputs.csv`: Updated December input file containing model predictions.

\- `score.py`: Official scoring and verification script provided by Spotter.

\- `scorer\_results/candidate\_december.png`: Generated visualization for December predictions.

\- `requirements.txt`: Python package dependencies.



\---



\## ⚙️ Requirements \& Installation



To install the required dependencies, run:

```bash

pip install -r requirements.txt


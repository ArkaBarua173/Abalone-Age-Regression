# Abalone Age Regression Problem

## 🔗 Link - (https://www.kaggle.com/code/arkabarua173/regression-of-abalone-age)

## 📌 Objective:
- Predicting the probabilities of exiting the bank.

## 📄 Dataset Description:
- **Sex**: Sex of the Abalone - Male(M), Female(F), Infant(I).
- **Length**: The length of the abalone in millimeters (mm).
- **Diameter**: The diameter of the abalone in millimeters (mm).
- **Height**: The height of the abalone in millimeters (mm).
- **Whole Weight**: The whole weight of the abalone in grams (g).
- **Whole weight.1**: The weight of the meat of the abalone in grams (g). Shucked Weight in the original dataset.
- **Whole weight.2**: The weight of the gut (viscera) of the abalone after bleeding in grams (g). Viscera Weight in the original dataset.
- **Shell Weight**: The weight of the abalone's shell after being dried in grams (g).
- **Rings**: The number of rings on the shell, which is a proxy for the age of the abalone.

## 🔨 Data Preprocessing
- **RobustScaler** is used for continous numerical values.
- **One Hot Encoder** used for categorical value (In this dataset (Sex)).
- **Natural logarithm plus one transformation** is applied to target variable (Rings) before fitting the model as values of Rings skewed. This transformation make the distribution mitigate the effect of extreme values and make the distribution more normal-like. Also, `np.expm1` is used to inverse the transformation so the target variable is back to it's original scale before returning them.

## 🤖 Model:
1. XGBRegressor
2. CatBoostRegressor
3. LGBMRegressor
4. Voting Regressor ( XGBRegressor + CatBoostRegressor + LGBMRegressor )

## 🔍 Model Evaluation:
- The main evaluation metric used is Root Mean Squared Logarithmic Error.
  
![result](/Snapshots/result.png)

- Feature Importance bar graph for 3 models are shown below

![Feature Importance](/Snapshots/FeatureImportance.png)







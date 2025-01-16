# Enhanced Dielectric Properties Prediction Model

## Overview
This project implements an advanced machine learning model for predicting dielectric properties of materials, improving upon the methodology presented in "Dielectric Characterization and Machine Learning-Based Predictions in Polymer Composites with Mixed Nanoparticles" (Journal of Macromolecular Science, 2024).

## Features
- Enhanced prediction of dielectric constant, dielectric loss, and AC conductivity
- Advanced feature engineering with polynomial interactions
- Temperature-frequency interaction analysis
- Comprehensive visualization suite
- Improved accuracy over baseline methods

## Requirements
```python
numpy>=1.21.0
pandas>=1.3.0
scikit-learn>=1.0.0
catboost>=1.0.0
optuna>=2.10.0
matplotlib>=3.4.0
seaborn>=0.11.0
```

## Usage
The main implementation is provided in `dielectric_prediction.ipynb`. To use:

1. Prepare your data files:
   - `dielectric_constant.csv`
   - `dielectric_loss.csv`
   - `ac_conductivity.csv`

2. Data format:
   ```
   Frequency (Hz), 30 C, 50 C, 100 C, 150 C, 200 C
   value1, dc1, dc2, dc3, dc4, dc5
   value2, dc1, dc2, dc3, dc4, dc5
   ...
   ```

3. Run the notebook:
   ```python
   # Example usage
   X, y_dielectric, y_loss, y_conductivity = prepare_data(
       'dielectric_constant.csv',
       'dielectric_loss.csv',
       'ac_conductivity.csv'
   )
   
   predictor = AdvancedDielectricPredictor()
   predictor.fit(X_train, y_train)
   results = predictor.evaluate(X_test, y_test)
   ```

## Model Performance

### AC Conductivity
```
Training: R² = 1.000000, RMSE = 0.000000
Testing:  R² = 0.979843, RMSE = 0.000352
```

### Dielectric Constant
```
Training: R² = 0.999997, RMSE = 0.199947
Testing:  R² = 0.998547, RMSE = 4.473997
```

### Dielectric Loss
```
Training: R² = 1.000000, RMSE = 0.000021
Testing:  R² = 0.946957, RMSE = 0.560140
```

## Key Improvements

### Feature Engineering
- Log transformation of frequency values
- Polynomial feature generation (degree=2)
- Temperature-frequency interaction terms
- Standardized scaling

### Model Optimization
- Extended hyperparameter optimization
- Early stopping mechanism
- Temperature-stratified sampling
- Comprehensive cross-validation

### Visualization Suite
- Prediction accuracy plots
- Error distribution analysis
- Feature importance visualization
- Temperature-frequency interaction heatmaps
- Residual analysis plots

## Example Outputs

### Prediction Accuracy
![Dielectric Constant Prediction](results/dielectric_constant_pred.png)
- Near-perfect correlation between predicted and actual values
- Consistent performance across temperature ranges
- Clear visualization of prediction accuracy

### Error Analysis
![Error Analysis](results/error_heatmap.png)
- Temperature-frequency interaction patterns
- Error distribution across operating conditions
- Identification of challenging regions

## Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

## Acknowledgments
- Original research paper: "Dielectric Characterization and Machine Learning-Based Predictions in Polymer Composites with Mixed Nanoparticles"
- CatBoost team for their excellent gradient boosting implementation
- Scientific Python community for the tools and libraries

## Contact
Srikrishna S Kashyap - uplskash@ljmu.ac.uk
Project Link: https://github.com/skashyapsri/enhanced-dielectric-properties-prediction

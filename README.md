### Report

#### Problem Definition:
The task involved predicting four binary targets (`target_1`, `target_2`, `target_3`, `target_4`) for each client, with each target indicating whether a specific event occurred (value `1`) or not (value `0`). The main challenge was handling an imbalanced dataset, identifying meaningful patterns in client behavior, and developing an accurate predictive model.

#### Approach:
1. **Data Preparation:**
   - Initially downloaded the dataset but faced memory constraints on my machine. To overcome this, I sampled data by selecting 10 records per client. This provided a manageable subset while preserving a representative structure of the original data.
   
2. **Exploratory Data Analysis (EDA):**
   - Visualized feature distributions using histograms and matplotlib. The distributions showed that most features were neither uniformly nor normally distributed, highlighting potential challenges in applying basic machine learning models.

3. **Feature Engineering:**
   - Aggregated data over months and clients to create higher-level features. These included:
     - Movement diversity: capturing unique locations (geohashes).
     - Transaction statistics: total transaction amounts.
   - Addressed missing values (`NaNs`) by filling them with appropriate strategies (e.g., mean for numeric features).
   - Filtered the target DataFrame, balancing the dataset.

4. **Correlation and Insights:**
   - Investigated correlations between features and targets, revealing weak relationships. This highlighted the need for advanced techniques to uncover non-linear patterns.

5. **Model Training:**
   - Trained a baseline RandomForestClassifier using the processed features.
   - Evaluated performance with sklearn's classification report. The results were suboptimal, reflecting the need for additional feature exploration and advanced modeling.
   - Tried to improve the result by apllying **cross-validation** and **xgboost**.

6. **Results and Challenges:**
   - Achieved a baseline model but with weak predictive performance. Factors contributing to this include:
     - Imbalanced target distribution.
     - Limited processing power, restricting the dataset size.
     - Weak correlations between features and targets.

#### Suggestions for Improvement:
- **Data Improvements:**
  - Use additional data or more detailed metadata if available.
  - Reduce dimensionality using PCA or feature selection techniques to highlight key patterns.
  
- **Modeling Enhancements:**
  - Experiment with gradient boosting methods (e.g., LightGBM).
  - Explore deep learning architectures, such as feedforward neural networks.
  - Apply feature interaction techniques or automated feature selection tools.
  
- **Insights Extraction:**
  - Perform clustering to group clients with similar behaviors.
  - Use advanced time-series techniques to capture temporal patterns.

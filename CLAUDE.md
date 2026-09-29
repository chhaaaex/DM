# Project: IE203 Data Mining Assignment 1 (Part A: Linear Regression, Part B: Classification)

## Deliverable rules (from the assignment)
- Only two notebooks are submitted: A1_LinearRegression_Template_Final.ipynb, A2_Classification_Template_Final.ipynb
- Every question = code cell + a short Markdown interpretation cell. No derivations/proofs.
- Datasets are in the SAME folder as the notebook. Use file names only: pd.read_csv("drug.csv"). Never absolute paths.
- The notebook must run top to bottom with "Restart & Run All" without errors.
- Do NOT put long study explanations inside the submission notebooks. Study material goes to study/ (not submitted).

## Technical rules
- p-values / significance: statsmodels (sklearn gives none). Logistic coefficients for inference: sm.Logit.
- Simulation: rng = np.random.default_rng(7) created ONCE outside any loop. scale= is the standard deviation (X: 1.5, noise: 0.6), never the variance.
- Classification: no train/test split is specified in the assignment, so use stratified split (random_state fixed), choose K by cross-validation on train only, report final metrics on test. State this decision in a Markdown cell.
- KNN: Pipeline with MinMaxScaler (assignment footnote says "same range"). Never fit the scaler on the full data.
- Do not use LogisticRegression(multi_class=...) (deprecated). Default lbfgs gives multinomial for 3+ classes.
- breast cancer: target 0 = malignant, 1 = benign. For precision/recall/F1 use pos_label=0.
- Verify important numbers against theory (e.g. SD of beta1_hat ≈ sigma / (sigma_X * sqrt(n))) and print the check.

## Terminology
Write Markdown interpretations using the lecture-slide vocabulary in slides/: confounding, flexibility, bias-variance trade-off, overfitting, Bayes classifier, training vs test error, log odds, baseline class. Keep original English terms.

## Code style (I must memorize this code)
- Reuse the SAME code pattern every time the same task appears (OLS, Logit, Pipeline+CV, metrics). Same variable names, same order.
- Short, flat, readable. No classes, no helper-function jungles, no clever one-liners.
- Every code cell starts with a 1-line comment: what it answers.

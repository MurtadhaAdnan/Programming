# Scikit-learn Functions by Expertise Level

## `Introduction`
**Scikit-learn** is the most popular machine learning library in Python:

- ✅ Ready-to-use ML algorithms
- ✅ Data preprocessing tools
- ✅ Easy model evaluation

## `Core Advantages`

| Feature | Description |
|--------|-------|
| ⚡ Easy to use | Consistent interface for all algorithms |
| 🧠 Powerful performance | Built on NumPy and SciPy |
| 📊 Excellent documentation | Clear and comprehensive examples |

---
<br><br><br>

## `Beginner Level`

| Function | Description | Example | Output |
|--------|-------|------|---------|
| `train_test_split()` | Split data | `X_train, X_test, y_train, y_test = train_test_split(X, y)` | Split datasets |
| `StandardScaler()` | Standardize data | `scaler = StandardScaler().fit(X)` | Standardized data |
| `LinearRegression()` | Linear regression | `model = LinearRegression()` | Regression model |
| `fit()` | Train model | `model.fit(X_train, y_train)` | Trained model |
| `predict()` | Make predictions | `y_pred = model.predict(X_test)` | Model predictions |
| `accuracy_score()` | Classification accuracy | `accuracy_score(y_test, y_pred)` | Accuracy value |
| `confusion_matrix()` | Confusion matrix | `confusion_matrix(y_test, y_pred)` | Classification performance |
| `KMeans()` | Clustering | `kmeans = KMeans(n_clusters=3)` | Clustering model |
| `PCA()` | Dimensionality reduction | `pca = PCA(n_components=2)` | Reduced data |
| `LabelEncoder()` | Label encoding | `encoder = LabelEncoder().fit(y)` | Encoded labels |

---
<br><br><br>

## `Intermediate Level`

| Function | Description | Example | Output |
|--------|-------|------|---------|
| `Pipeline()` | Process chaining | `pipe = Pipeline([('scaler', StandardScaler()), ('svm', SVC())])` | Processing pipeline |
| `GridSearchCV()` | Hyperparameter tuning | `grid = GridSearchCV(estimator, param_grid)` | Best parameters |
| `RandomForestClassifier()` | Random forest | `model = RandomForestClassifier()` | Ensemble classifier |
| `SVC()` | Support Vector Machine | `svm = SVC(kernel='rbf')` | SVM classifier |
| `metrics` | Evaluation metrics | `precision_recall_fscore_support(y_test, y_pred)` | Precision metrics |
| `OneHotEncoder()` | Categorical encoding | `encoder = OneHotEncoder().fit(X)` | Categorical features |
| `FeatureUnion()` | Feature combination | `union = FeatureUnion([('pca', PCA()), ('select', SelectKBest())])` | Combined features |
| `cross_val_score()` | Cross-validation | `scores = cross_val_score(model, X, y, cv=5)` | Validation scores |
| `GradientBoostingClassifier()` | Gradient boosting | `gb = GradientBoostingClassifier()` | Boosted classifier |
| `make_classification()` | Synthetic data | `X, y = make_classification(n_samples=100)` | Test data |

---
<br><br><br>

## `Advanced Level`

| Function | Description | Example | Output |
|--------|-------|------|---------|
| `ColumnTransformer()` | Column-wise transformations | `transformer = ColumnTransformer([('num', scaler, num_cols)])` | Selective transformation |
| `BayesianGaussianMixture()` | Bayesian GMM | `bgm = BayesianGaussianMixture(n_components=3)` | Probabilistic clustering |
| `IsolationForest()` | Anomaly detection | `iso = IsolationForest(contamination=0.1)` | Anomaly detector |
| `TSNE()` | Dimensionality reduction | `tsne = TSNE(n_components=2)` | Data visualization |
| `CalibratedClassifierCV()` | Probability calibration | `calib = CalibratedClassifierCV(model, cv=3)` | Calibrated probabilities |
| `FeatureImportances` | Feature importance | `model.feature_importances_` | Feature rankings |
| `PartialDependenceDisplay` | Partial dependence | `PartialDependenceDisplay.from_estimator(model, X, features)` | Model interpretation |
| `SpectralClustering()` | Spectral clustering | `spec = SpectralClustering(n_clusters=3)` | Non-linear clustering |
| `StackingClassifier()` | Model stacking | `stack = StackingClassifier(estimators=[...])` | Meta-classifier |
| `Optics()` | Density clustering | `optics = OPTICS(min_samples=5)` | Advanced clustering |

---
<br><br><br>

## `Expert Level`

| Function | Description | Example | Output |
|--------|-------|------|---------|
| `create_dataset()` | Custom data generation | `dataset = create_dataset(custom_generator)` | Dynamic datasets |
| `custom_scorer()` | Custom metrics | `scorer = make_scorer(custom_loss_func)` | Custom evaluation |
| `FunctionTransformer()` | Custom transformations | `transformer = FunctionTransformer(my_func)` | Custom processing |
| `meta-estimators` | Custom estimators | `class MyMetaEstimator(BaseEstimator): ...` | Custom algorithm |
| `joblib` | Parallel processing | `Parallel(n_jobs=4)(delayed(func)(i) for i in range(10))` | Parallel execution |
| `neural_network` | Neural networks | `MLPClassifier(hidden_layer_sizes=(100,))` | Basic NN |
| `KernelApproximation` | Kernel approximation | `rbf = RBFSampler(gamma=1)` | Kernel transformation |
| `IsotonicRegression()` | Isotonic regression | `iso_reg = IsotonicRegression()` | Non-linear regression |
| `GaussianProcess()` | Gaussian processes | `gp = GaussianProcessRegressor()` | Probabilistic model |
| `OutlierDetection` | Custom anomaly detection | `class MyOutlierDetector(OutlierMixin): ...` | Custom anomaly algorithm |
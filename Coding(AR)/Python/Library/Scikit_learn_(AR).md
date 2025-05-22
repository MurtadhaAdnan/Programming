# دوال Scikit-learn حسب مستوى الخبرة

## `المقدمة`
**Scikit-learn** هي المكتبة الأشهر للتعلم الآلي في بايثون:

- ✅ خوارزميات تعلم آلي جاهزة
- ✅ أدوات معالجة البيانات
- ✅ تقييم النماذج بسهولة

## `المزايا الأساسية`

| الميزة | الشرح |
|--------|-------|
| ⚡ سهولة الاستخدام | واجهة موحدة لجميع الخوارزميات |
| 🧠 أداء قوي | معتمدة على NumPy وSciPy |
| 📊 توثيق ممتاز | أمثلة واضحة وشاملة |

---
<br><br><br>

## `المستوى المبتدئ`

| الدالة | الوصف | مثال | النتيجة |
|--------|-------|------|---------|
| `train_test_split()` | تقسيم البيانات | `X_train, X_test, y_train, y_test = train_test_split(X, y)` | بيانات مقسمة |
| `StandardScaler()` | تسوية البيانات | `scaler = StandardScaler().fit(X)` | بيانات معيارية |
| `LinearRegression()` | انحدار خطي | `model = LinearRegression()` | نموذج انحدار |
| `fit()` | تدريب النموذج | `model.fit(X_train, y_train)` | نموذج مدرب |
| `predict()` | التنبؤ | `y_pred = model.predict(X_test)` | توقعات النموذج |
| `accuracy_score()` | دقة التصنيف | `accuracy_score(y_test, y_pred)` | قيمة الدقة |
| `confusion_matrix()` | مصفوفة الارتباك | `confusion_matrix(y_test, y_pred)` | أداء التصنيف |
| `KMeans()` | التجميع | `kmeans = KMeans(n_clusters=3)` | نموذج تجميع |
| `PCA()` | تخفيض الأبعاد | `pca = PCA(n_components=2)` | بيانات مخفضة |
| `LabelEncoder()` | ترميز التصنيفات | `encoder = LabelEncoder().fit(y)` | تسميات مرمزة |

---
<br><br><br>

## `المستوى المتوسط`

| الدالة | الوصف | مثال | النتيجة |
|--------|-------|------|---------|
| `Pipeline()` | سلسلة عمليات | `pipe = Pipeline([('scaler', StandardScaler()), ('svm', SVC())])` | خط أنابيب |
| `GridSearchCV()` | ضبط المعاملات | `grid = GridSearchCV(estimator, param_grid)` | أفضل معاملات |
| `RandomForestClassifier()` | غابة عشوائية | `model = RandomForestClassifier()` | مصنف قوي |
| `SVC()` | آلة متجهات داعمة | `svm = SVC(kernel='rbf')` | مصنف SVM |
| `metrics` | مقاييس التقييم | `precision_recall_fscore_support(y_test, y_pred)` | مقاييس دقيقة |
| `OneHotEncoder()` | ترميز فئوي | `encoder = OneHotEncoder().fit(X)` | بيانات فئوية |
| `FeatureUnion()` | دمج الميزات | `union = FeatureUnion([('pca', PCA()), ('select', SelectKBest())])` | ميزات مجمعة |
| `cross_val_score()` | تقييم متقاطع | `scores = cross_val_score(model, X, y, cv=5)` | تقييم موثوق |
| `GradientBoostingClassifier()` | تعزيز متدرج | `gb = GradientBoostingClassifier()` | مصنف قوي |
| `make_classification()` | بيانات اصطناعية | `X, y = make_classification(n_samples=100)` | بيانات تجريبية |

---
<br><br><br>

## `المستوى المتقدم`

| الدالة | الوصف | مثال | النتيجة |
|--------|-------|------|---------|
| `ColumnTransformer()` | تحويل أعمدة | `transformer = ColumnTransformer([('num', scaler, num_cols)])` | تحويل انتقائي |
| `BayesianGaussianMixture()` | نموذج بيزي | `bgm = BayesianGaussianMixture(n_components=3)` | تجميع احتمالي |
| `IsolationForest()` | كشف شذوذ | `iso = IsolationForest(contamination=0.1)` | نموذج شذوذ |
| `TSNE()` | تخفيض أبعاد | `tsne = TSNE(n_components=2)` | تصور البيانات |
| `CalibratedClassifierCV()` | معايرة الاحتمالات | `calib = CalibratedClassifierCV(model, cv=3)` | احتمالات دقيقة |
| `FeatureImportances` | أهمية الميزات | `model.feature_importances_` | ترتيب الميزات |
| `PartialDependenceDisplay` | اعتماد جزئي | `PartialDependenceDisplay.from_estimator(model, X, features)` | تفسير النموذج |
| `SpectralClustering()` | تجميع طيفي | `spec = SpectralClustering(n_clusters=3)` | تجميع غير خطي |
| `StackingClassifier()` | دمج نماذج | `stack = StackingClassifier(estimators=[...])` | نموذج مركب |
| `Optics()` | تجميع كثافة | `optics = OPTICS(min_samples=5)` | تجميع متقدم |

---
<br><br><br>

## `مستوى الخبير`

| الدالة | الوصف | مثال | النتيجة |
|--------|-------|------|---------|
| `create_dataset()` | بيانات مخصصة | `dataset = create_dataset(custom_generator)` | بيانات ديناميكية |
| `custom_scorer()` | مقياس مخصص | `scorer = make_scorer(custom_loss_func)` | تقييم مخصص |
| `FunctionTransformer()` | تحويل مخصص | `transformer = FunctionTransformer(my_func)` | معالجة مخصصة |
| `meta-estimators` | نماذج ميتا | `class MyMetaEstimator(BaseEstimator): ...` | خوارزمية مخصصة |
| `joblib` | معالجة متوازية | `Parallel(n_jobs=4)(delayed(func)(i) for i in range(10))` | تنفيذ متوازي |
| `neural_network` | شبكات عصبية | `MLPClassifier(hidden_layer_sizes=(100,))` | شبكة بسيطة |
| `KernelApproximation` | تقريب النواة | `rbf = RBFSampler(gamma=1)` | تحويل النواة |
| `IsotonicRegression()` | انحدار متساوي القياس | `iso_reg = IsotonicRegression()` | انحدار غير خطي |
| `GaussianProcess()` | عمليات غاوسية | `gp = GaussianProcessRegressor()` | نموذج احتمالي |
| `OutlierDetection` | كشف شذوذ مخصص | `class MyOutlierDetector(OutlierMixin): ...` | خوارزمية شذوذ مخصصة |
# دوال TensorFlow و Keras حسب مستوى الخبرة

## `المقدمة`
**TensorFlow** و **Keras** من أقوى مكتبات التعلم العميق:

- ✅ بناء نماذج الشبكات العصبية
- ✅ معالجة البيانات الرقمية
- ✅ دعم GPU/TPU لتسريع الحسابات

## `الفوائد الأساسية`

| الميزة | التوضيح |
|--------|---------|
| ⚡ الأداء السريع | تسريع العمليات باستخدام GPU |
| 🧠 نماذج جاهزة | طبقات وشبكات مبنية مسبقاً |
| 📊 تصور البيانات | أدوات لعرض النتائج والتدريب |

---
<div dir="rtl">
<br><br><br>

## `المستوى المبتدئ`

| الدالة | الوصف | مثال | النتيجة |
|--------|-------|------|---------|
| `tf.constant(value)` | إنشاء تنسور ثابت | `tf.constant([1, 2, 3])` | `[1 2 3]` |
| `tf.Variable(initial_value)` | إنشاء تنسور متغير | `tf.Variable([1.0, 2.0])` | `[1.0, 2.0]` (قابل للتعديل) |
| `tf.zeros(shape)` | إنشاء تنسور مملوء بأصفار | `tf.zeros([2, 3])` | `[[0. 0. 0.], [0. 0. 0.]]` |
| `tf.ones(shape)` | إنشاء تنسور مملوء بواحدات | `tf.ones([2])` | `[1. 1.]` |
| `tf.reshape(tensor, shape)` | تغيير شكل التنسور | `tf.reshape([1,2,3,4], [2,2])` | `[[1 2], [3 4]]` |
| `tf.random.normal(shape)` | إنشاء تنسور بقيم عشوائية | `tf.random.normal([2])` | `[0.12, -0.45]` (قيم عشوائية) |
| `tf.concat([t1, t2], axis)` | دمج تنسورات | `tf.concat([[1],[2]], [[3],[4]], 0)` | `[[1], [2], [3], [4]]` |
| `tf.math.add(x, y)` | جمع تنسورات | `tf.math.add([1,2], [3,4])` | `[4 6]` |
| `tf.math.reduce_mean(input)` | حساب المتوسط | `tf.math.reduce_mean([1.,2.,3.])` | `2.0` |
| `keras.Sequential(layers)` | نموذج تسلسلي | `Sequential([Dense(2)])` | نموذج به طبقة واحدة |
<br><br><br>

## `المستوى المتوسط`

| الدالة | الوصف | مثال | النتيجة |
|--------|-------|------|---------|
| `tf.data.Dataset.from_tensor_slices(data)` | إنشاء مجموعة بيانات | `Dataset.from_tensor_slices([1,2,3])` | كائن Dataset يحتوي على البيانات |
| `tf.image.resize(images, size)` | تغيير حجم الصور | `tf.image.resize([[1,2],[3,4]], [4,4])` | مصفوفة 4x4 |
| `keras.layers.Conv2D(filters, kernel_size)` | طبقة التلافيف | `Conv2D(32, 3)(input)` | تنسور بمعالم تلافيفية |
| `keras.layers.LSTM(units)` | طبقة LSTM | `LSTM(64)(input)` | تنسور بمعالم LSTM |
| `keras.optimizers.Adam(learning_rate)` | محسن Adam | `optimizers.Adam(0.001)` | كائن المحسن |
| `keras.losses.SparseCategoricalCrossentropy()` | دالة الخسارة | `loss_fn = SparseCategoricalCrossentropy()` | دالة خسارة جاهزة |
| `model.compile(optimizer, loss)` | تهيئة النموذج | `model.compile('adam', 'mse')` | نموذج جاهز للتدريب |
| `model.fit(x, y, epochs)` | تدريب النموذج | `fit(x_train, y_train, epochs=10)` | تاريخ التدريب |
| `model.evaluate(x, y)` | تقييم النموذج | `evaluate(x_test, y_test)` | قيمة الخسارة والدقة |
| `model.predict(x)` | عمل تنبؤات | `predict([[1.0, 2.0]])` | مصفوفة التنبؤات |

<br><br><br>

## `المستوى المتقدم`

| الدالة | الوصف | مثال | النتيجة |
|--------|-------|------|---------|
| `@tf.function` | تحويل الدوال لرسم بياني | `@tf.function\ndef add(x): return x+1` | دالة محسنة للأداء |
| `tf.GradientTape()` | تسجيل العمليات | `with GradientTape() as tape:\n y=x**2` | كائن لحساب التدرجات |
| `tape.gradient(target, sources)` | حساب التدرجات | `tape.gradient(y, x)` | تدرج y بالنسبة لـ x |
| `keras.Model(inputs, outputs)` | نموذج مخصص | `Model(inputs, outputs)` | نموذج قابل للتدريب |
| `tf.saved_model.save(model, path)` | حفظ النموذج | `saved_model.save(model, 'path')` | نموذج محفوظ |
| `tf.saved_model.load(path)` | تحميل النموذج | `tf.saved_model.load('path')` | نموذج محمل |
| `tf.distribute.MirroredStrategy()` | تدريب موزع | `with MirroredStrategy().scope():` | سياق التدريب الموزع |
| `tf.lite.TFLiteConverter` | تحويل النموذج | `TFLiteConverter.from_keras_model(model)` | محول للنموذج الخفيف |
| `tf.keras.utils.plot_model()` | تصور النموذج | `plot_model(model, show_shapes=True)` | رسم بياني للنموذج |
| `tf.keras.callbacks.TensorBoard()` | تصور التدريب | `callbacks.TensorBoard(log_dir)` | كائن TensorBoard |

<br><br><br>

## `المستوى الخبير`

| الدالة | الوصف | مثال | النتيجة |
|--------|-------|------|---------|
| `tf.custom_gradient` | تدرجات مخصصة | `@tf.custom_gradient\ndef custom_op(x):` | عملية ذات تدرج مخصص |
| `tf.py_function(func, inp, Tout)` | دالة بايثون في TF | `tf.py_function(func, [x], tf.float32)` | دالة بايثون في الرسم البياني |
| `tf.raw_ops` | عمليات منخفضة المستوى | `tf.raw_ops.Add(x=x, y=y)` | عملية إضافة مباشرة |
| `tf.autodiff.ForwardAccumulator` | تفاضل أمامي | `acc = ForwardAccumulator(x, dx)` | حساب التفاضل الأمامي |
| `tf.config.optimizer.set_jit()` | تمكين JIT | `tf.config.optimizer.set_jit(True)` | تمكين التحويل البرمجي |
| `tf.debugging.enable_check_numerics()` | تصحيح القيم | `tf.debugging.enable_check_numerics()` | كشف القيم غير العددية |
| `tf.config.experimental` | إعدادات تجريبية | `tf.config.experimental_run_functions_eagerly(True)` | تشغيل الدوال فوراً |
| `tf.linalg` | عمليات جبر خطي | `tf.linalg.inv(matrix)` | معكوس المصفوفة |
| `tf.signal` | معالجة الإشارة | `tf.signal.fft(signal)` | تحويل فورييه السريع |
| `tf.random.Generator` | مولد أرقام عشوائية | `gen = tf.random.Generator.from_seed(123)` | مولد عشوائي مسيطر عليه |

</div>
# TensorFlow and Keras Functions by Expertise Level

## `Introduction`
**TensorFlow** and **Keras** are among the most powerful deep learning libraries:

- ✅ Building neural network models
- ✅ Processing numerical data
- ✅ GPU/TPU support for accelerated computations

## `Core Benefits`

| Feature | Explanation |
|---------|-------------|
| ⚡ Fast Performance | Accelerated operations using GPU |
| 🧠 Ready-made Models | Pre-built layers and networks |
| 📊 Data Visualization | Tools to display results and training |

---

## `Beginner Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `tf.constant(value)` | Create constant tensor | `tf.constant([1, 2, 3])` | `[1 2 3]` |
| `tf.Variable(initial_value)` | Create variable tensor | `tf.Variable([1.0, 2.0])` | `[1.0, 2.0]` (modifiable) |
| `tf.zeros(shape)` | Create zero-filled tensor | `tf.zeros([2, 3])` | `[[0. 0. 0.], [0. 0. 0.]]` |
| `tf.ones(shape)` | Create one-filled tensor | `tf.ones([2])` | `[1. 1.]` |
| `tf.reshape(tensor, shape)` | Reshape tensor | `tf.reshape([1,2,3,4], [2,2])` | `[[1 2], [3 4]]` |
| `tf.random.normal(shape)` | Create random-valued tensor | `tf.random.normal([2])` | `[0.12, -0.45]` (random values) |
| `tf.concat([t1, t2], axis)` | Concatenate tensors | `tf.concat([[1],[2]], [[3],[4]], 0)` | `[[1], [2], [3], [4]]` |
| `tf.math.add(x, y)` | Add tensors | `tf.math.add([1,2], [3,4])` | `[4 6]` |
| `tf.math.reduce_mean(input)` | Calculate mean | `tf.math.reduce_mean([1.,2.,3.])` | `2.0` |
| `keras.Sequential(layers)` | Sequential model | `Sequential([Dense(2)])` | Model with one layer |

---

## `Intermediate Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `tf.data.Dataset.from_tensor_slices(data)` | Create dataset | `Dataset.from_tensor_slices([1,2,3])` | Dataset object containing data |
| `tf.image.resize(images, size)` | Resize images | `tf.image.resize([[1,2],[3,4]], [4,4])` | 4x4 matrix |
| `keras.layers.Conv2D(filters, kernel_size)` | Convolution layer | `Conv2D(32, 3)(input)` | Tensor with convolution features |
| `keras.layers.LSTM(units)` | LSTM layer | `LSTM(64)(input)` | Tensor with LSTM features |
| `keras.optimizers.Adam(learning_rate)` | Adam optimizer | `optimizers.Adam(0.001)` | Optimizer object |
| `keras.losses.SparseCategoricalCrossentropy()` | Loss function | `loss_fn = SparseCategoricalCrossentropy()` | Ready loss function |
| `model.compile(optimizer, loss)` | Configure model | `model.compile('adam', 'mse')` | Model ready for training |
| `model.fit(x, y, epochs)` | Train model | `fit(x_train, y_train, epochs=10)` | Training history |
| `model.evaluate(x, y)` | Evaluate model | `evaluate(x_test, y_test)` | Loss and accuracy values |
| `model.predict(x)` | Make predictions | `predict([[1.0, 2.0]])` | Prediction array |

---

## `Advanced Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `@tf.function` | Convert functions to graph | `@tf.function\ndef add(x): return x+1` | Performance-optimized function |
| `tf.GradientTape()` | Record operations | `with GradientTape() as tape:\n y=x**2` | Object for gradient calculation |
| `tape.gradient(target, sources)` | Calculate gradients | `tape.gradient(y, x)` | Gradient of y w.r.t x |
| `keras.Model(inputs, outputs)` | Custom model | `Model(inputs, outputs)` | Trainable model |
| `tf.saved_model.save(model, path)` | Save model | `saved_model.save(model, 'path')` | Saved model |
| `tf.saved_model.load(path)` | Load model | `tf.saved_model.load('path')` | Loaded model |
| `tf.distribute.MirroredStrategy()` | Distributed training | `with MirroredStrategy().scope():` | Distributed training context |
| `tf.lite.TFLiteConverter` | Model conversion | `TFLiteConverter.from_keras_model(model)` | Lite model converter |
| `tf.keras.utils.plot_model()` | Visualize model | `plot_model(model, show_shapes=True)` | Model graph |
| `tf.keras.callbacks.TensorBoard()` | Visualize training | `callbacks.TensorBoard(log_dir)` | TensorBoard object |

---

## `Expert Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `tf.custom_gradient` | Custom gradients | `@tf.custom_gradient\ndef custom_op(x):` | Operation with custom gradient |
| `tf.py_function(func, inp, Tout)` | Python function in TF | `tf.py_function(func, [x], tf.float32)` | Python function in graph |
| `tf.raw_ops` | Low-level operations | `tf.raw_ops.Add(x=x, y=y)` | Direct add operation |
| `tf.autodiff.ForwardAccumulator` | Forward differentiation | `acc = ForwardAccumulator(x, dx)` | Forward differentiation calculation |
| `tf.config.optimizer.set_jit()` | Enable JIT | `tf.config.optimizer.set_jit(True)` | Enable compilation |
| `tf.debugging.enable_check_numerics()` | Debug values | `tf.debugging.enable_check_numerics()` | Detect non-numerical values |
| `tf.config.experimental` | Experimental settings | `tf.config.experimental_run_functions_eagerly(True)` | Run functions immediately |
| `tf.linalg` | Linear algebra operations | `tf.linalg.inv(matrix)` | Matrix inverse |
| `tf.signal` | Signal processing | `tf.signal.fft(signal)` | Fast Fourier transform |
| `tf.random.Generator` | Random number generator | `gen = tf.random.Generator.from_seed(123)` | Controlled random generator |
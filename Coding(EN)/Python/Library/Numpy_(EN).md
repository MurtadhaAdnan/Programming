# `NumPy Functions by Skill Level`<br>
# NumPy: The Fundamental Package for Scientific Computing in Python


## `Overview`
**NumPy** (Numerical Python) is the core library for numerical computing in Python. It provides:

- High-performance multidimensional **array `objects`**
- Tools for working with these arrays
- Mathematical functions for array operations <br><br>

## `Key Benefits`

| Feature | Description |
|---------|-------------|
| 🚀 **Performance** | Optimized C-based operations (faster than Python lists) |
| 🔢 **N-dimensional Arrays** | Powerful ndarray object for vectors, matrices, and tensors |
| 🧮 **Vectorization** | Eliminates loops via array broadcasting |
| 🔬 **Scientific Foundation** | Base for nearly all Python data science tools |

___

<br><br><br>


# `Beginner Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `np.array()` | Create an array from given data | `np.array([1, 2, 3])` | `array([1, 2, 3])` |
| `np.zeros()` | Create an array filled with zeros | `np.zeros((2, 3))` | `array([[0., 0., 0.], [0., 0., 0.]])` |
| `np.ones()` | Create an array filled with ones | `np.ones((2, 2))` | `array([[1., 1.], [1., 1.]])` |
| `np.arange()` | Create array with evenly spaced values | `np.arange(0, 10, 2)` | `array([0, 2, 4, 6, 8])` |
| `np.linspace()` | Create array with specified number of evenly spaced values | `np.linspace(0, 1, 5)` | `array([0., 0.25, 0.5, 0.75, 1.])` |
| `np.shape` | Get array dimensions | `np.array([[1,2],[3,4]]).shape` | `(2, 2)` |
| `np.reshape()` | Change array shape without changing data | `np.arange(6).reshape(2, 3)` | `array([[0, 1, 2], [3, 4, 5]])` |
| `np.sum()` | Sum of array elements | `np.sum([1, 2, 3])` | `6` |
| `np.mean()` | Arithmetic mean | `np.mean([1, 2, 3, 4])` | `2.5` |
| `np.max()/np.min()` | Maximum/minimum value | `np.max([1, 3, 2])` | `3` |
<br><br><br>

# `Intermediate Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `np.random.rand()` | Random values in given shape | `np.random.rand(2, 2)` | `array([[0.42, 0.48], [0.18, 0.33]])` (example) |
| `np.concatenate()` | Join arrays along an axis | `np.concatenate(([1,2], [3,4]))` | `array([1, 2, 3, 4])` |
| `np.vstack()/np.hstack()` | Stack arrays vertically/horizontally | `np.vstack(([1,2], [3,4]))` | `array([[1, 2], [3, 4]])` |
| `np.transpose()` | Transpose array | `np.transpose([[1,2], [3,4]])` | `array([[1, 3], [2, 4]])` |
| `np.dot()` | Dot product of two arrays | `np.dot([1,2], [3,4])` | `11` |
| `np.where()` | Return elements based on condition | `np.where([True, False, True], 1, 0)` | `array([1, 0, 1])` |
| `np.unique()` | Unique elements in array | `np.unique([1, 1, 2, 2, 3])` | `array([1, 2, 3])` |
| `np.sort()` | Sort an array | `np.sort([3, 1, 2])` | `array([1, 2, 3])` |
| `np.argmax()/np.argmin()` | Indices of max/min values | `np.argmax([1, 3, 2])` | `1` |
| `np.loadtxt()/np.savetxt()` | Read/write from/to text file | `np.savetxt('data.txt', [1,2,3])` | (saves to file) |

<br><br><br>


# `Advanced Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `np.meshgrid()` | Create coordinate matrices | `x, y = np.meshgrid([1,2], [3,4])` | Two 2x2 arrays |
| `np.einsum()` | Einstein summation convention | `np.einsum('ii', [[1,2],[3,4]])` | `5` (trace) |
| `np.polyfit()` | Least squares polynomial fit | `np.polyfit([1,2,3], [1,4,9], 2)` | `array([1., 0., 0.])` (perfect fit) |
| `np.fft.fft()` | Fast Fourier Transform | `np.fft.fft([1, -1, 1, -1])` | Complex array of DFT |
| `np.linalg.svd()` | Singular Value Decomposition | `np.linalg.svd([[1,2],[3,4]])` | Tuple of U, S, Vh |
| `np.linalg.eig()` | Eigenvalues/vectors | `np.linalg.eig([[1, -1], [1, 1]])` | Complex eigenvalues/vectors |
| `np.pad()` | Pad array with values | `np.pad([1,2], (1,1), 'constant')` | `array([0, 1, 2, 0])` |
| `np.tile()` | Repeat array | `np.tile([1,2], 3)` | `array([1, 2, 1, 2, 1, 2])` |
| `np.vectorize()` | Vectorize a function | `vfunc = np.vectorize(lambda x: x*2)` | Vectorized function |
| `np.select()` | Return elements from choices based on conditions | `np.select([x<1,x>2], [x, x+10])` | Conditional selection |


<br><br><br>

# `Expert Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `np.lib.stride_tricks.as_strided()` | Create array view with custom strides | `as_strided(arr, shape=(3,3), strides=(8,8))` | Sliding window view |
| `np.recarray()` | Create record array | `np.recarray((2,), dtype=[('x', int), ('y', float)])` | Record array |
| `np.memmap()` | Memory-map to file | `np.memmap('data.dat', dtype='float32', mode='r', shape=(3,4))` | Memory-mapped array |
| `np.dtype()` | Create custom data type | `np.dtype([('name', 'S10'), ('age', 'i4')])` | Custom dtype object |
| `np.broadcast_to()` | Broadcast array to new shape | `np.broadcast_to([1,2,3], (3,3))` | Broadcasted array |
| `np.apply_along_axis()` | Apply function along axis | `np.apply_along_axis(np.sum, 0, [[1,2],[3,4]])` | `array([4, 6])` |
| `np.partition()` | Partition array around kth element | `np.partition([3,1,4,2], 2)` | `array([1, 2, 3, 4])` |
| `np.at()` | Perform operation at specified indices | `np.add.at(arr, [0,1], 10)` | In-place addition |
| `np.putmask()` | Set values based on mask | `np.putmask(arr, arr>5, 0)` | Modified array |
| `np.isin()` | Test if elements are in another array | `np.isin([1,2,3], [2,4])` | `array([False, True, False])` |

<br><br><br>
# `Master Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `np.nditer()` | Efficient multi-dimensional iterator | `for x in np.nditer(arr): print(x)` | Iterates through elements |
| `np.ufunc.reduceat()` | Reduce at specified indices | `np.add.reduceat([1,2,3,4], [0,2])` | `array([3, 7])` |
| `np.interp()` | One-dimensional linear interpolation | `np.interp(2.5, [1,2,3], [10,20,30])` | `25.0` |
| `np.gradient()` | Gradient of an array | `np.gradient([1,2,4,7])` | `array([1., 1.5, 2.5, 3.])` |
| `np.correlate()` | Cross-correlation | `np.correlate([1,2,3], [0,1,0.5])` | `3.5` |
| `np.histogramdd()` | Multi-dimensional histogram | `np.histogramdd(sample, bins=3)` | Histogram and edges |
| `np.polynomial` | Polynomial package | `np.polynomial.Polynomial.fit(x, y, 2)` | Polynomial object |
| `np.lib.mixins.NDArrayOperatorsMixin` | Create NumPy-compatible classes | `class MyArray(NDArrayOperatorsMixin): ...` | Custom array class |
| `np.einsum_path()` | Optimize einsum path | `np.einsum_path('ij,jk,kl->il', a, b, c)` | Optimization path |
| `np.can_cast()` | Check type casting possibility | `np.can_cast(np.int32, np.float64)` | `True` |
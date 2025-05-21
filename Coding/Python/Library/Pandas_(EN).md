# pandas Functions by Expertise Level

## `Introduction`
**pandas** is one of the most powerful data analysis libraries:

- ✅ Data manipulation and cleaning
- ✅ Handling structured data (DataFrames/Series)
- ✅ Integration with visualization and ML libraries

## `Core Benefits`

| Feature | Explanation |
|---------|-------------|
| ⚡ Fast Operations | Optimized for performance with C-based backend |
| 🧠 Flexible Data Structures | DataFrame and Series for varied data types |
| 📊 Built-in Visualization | Quick plotting with .plot() methods |

---
<br><br><br>

## `Beginner Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `pd.Series(data)` | Create a Series | `pd.Series([1, 2, 3])` | `0:1, 1:2, 2:3` |
| `pd.DataFrame(data)` | Create DataFrame | `pd.DataFrame({'A':[1,2]})` | DataFrame with column 'A' |
| `df.head(n)` | Show first n rows | `df.head(3)` | First 3 rows |
| `df.tail(n)` | Show last n rows | `df.tail(2)` | Last 2 rows |
| `df.shape` | Get dimensions | `df.shape` | `(rows, cols)` |
| `df.describe()` | Summary stats | `df.describe()` | Count/mean/std etc. |
| `df['col'].value_counts()` | Count unique values | `df['A'].value_counts()` | Value frequencies |
| `df.sort_values('col')` | Sort by column | `df.sort_values('A')` | Sorted DataFrame |
| `df.dropna()` | Remove missing values | `df.dropna()` | Cleaned DataFrame |
| `df.fillna(value)` | Fill missing values | `df.fillna(0)` | Filled DataFrame |

---

<br><br><br>

## `Intermediate Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `pd.read_csv(file)` | Read CSV file | `pd.read_csv('data.csv')` | Loaded DataFrame |
| `df.groupby('col')` | Group operations | `df.groupby('A').mean()` | Grouped aggregations |
| `df.merge(df2, on='col')` | Merge DataFrames | `df1.merge(df2, on='ID')` | Merged DataFrame |
| `df.pivot_table()` | Create pivot table | `df.pivot_table(values='B', index='A')` | Pivot table |
| `df.apply(func)` | Apply function | `df['A'].apply(lambda x: x*2)` | Transformed column |
| `pd.get_dummies(df)` | One-hot encoding | `pd.get_dummies(df['A'])` | Encoded DataFrame |
| `df.corr()` | Correlation matrix | `df.corr()` | Correlation values |
| `df.plot()` | Quick plotting | `df['A'].plot()` | Matplotlib plot |
| `df.to_csv(file)` | Save to CSV | `df.to_csv('out.csv')` | Saved file |
| `df.isna().sum()` | Count missing values | `df.isna().sum()` | Missing value counts |

---
<br><br><br>

## `Advanced Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `pd.melt(df)` | Unpivot DataFrame | `pd.melt(df, id_vars='A')` | Reshaped DataFrame |
| `df.pipe(func)` | Method chaining | `df.pipe(clean).pipe(transform)` | Processed DataFrame |
| `df.rolling(n).mean()` | Rolling calculations | `df['A'].rolling(3).mean()` | Rolling averages |
| `pd.qcut(df['col'], q)` | Quantile bins | `pd.qcut(df['A'], 4)` | Binned categories |
| `df.style` | Styling output | `df.style.background_gradient()` | Styled DataFrame |
| `pd.IntervalIndex` | Interval indexing | `pd.IntervalIndex.from_breaks([1,2,3])` | Interval index |
| `pd.api.extensions` | Extend pandas | Custom extension types | Extended functionality |
| `pd.eval()` | String expressions | `pd.eval("df.A + df.B")` | Evaluated result |
| `df.explode('col')` | Expand list items | `df.explode('list_col')` | Expanded rows |
| `df.to_parquet()` | Save as Parquet | `df.to_parquet('data.parquet')` | Binary file |

---
<br><br><br>

## `Expert Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `pd.DataFrame.sparse` | Sparse DataFrames | `df.sparse.from_spmatrix(matrix)` | Memory-efficient DF |
| `pd.io.formats.style` | Custom styling | Custom HTML/CSS styling | Publication-ready tables |
| `pd.testing` | Testing utilities | `pd.testing.assert_frame_equal()` | Unit test helpers |
| `pd.Grouper` | Advanced grouping | `df.groupby(pd.Grouper(key='date', freq='M'))` | Time-based grouping |
| `pd.DataFrame.attrs` | Metadata storage | `df.attrs['desc'] = "..."` | Attached metadata |
| `pd.core.groupby.DataFrameGroupBy.__iter__` | Group iteration | Custom group processing | Low-level control |
| `pd.api.types` | Type utilities | `pd.api.types.is_numeric_dtype()` | Type checking |
| `pd.io.sql` | SQL integration | `pd.read_sql(query, conn)` | Database operations |
| `pd.json_normalize()` | JSON flattening | `pd.json_normalize(nested_json)` | Flat DataFrame |
| `pd.set_eng_float_format()` | Display formatting | `pd.set_eng_float_format(accuracy=2)` | Engineering notation |
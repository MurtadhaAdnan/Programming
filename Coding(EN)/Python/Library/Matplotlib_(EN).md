# Matplotlib Functions by Expertise Level

## `Introduction`
**Matplotlib** is the fundamental plotting library for Python:

- ✅ Create publication-quality visualizations
- ✅ Support for various plot types (line, bar, scatter, etc.)
- ✅ Highly customizable and extensible

## `Core Benefits`

| Feature | Explanation |
|---------|-------------|
| ⚡ Versatile Plotting | Supports 2D and 3D visualizations |
| 🧠 Python Integration | Works seamlessly with NumPy and Pandas |
| 📊 Customization | Fine control over every plot element |

---
<br><br><br>

## `Beginner Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `plt.plot(x, y)` | Basic line plot | `plt.plot([1,2,3], [1,4,9])` | Simple line chart |
| `plt.scatter(x, y)` | Scatter plot | `plt.scatter(x, y)` | Points plot |
| `plt.bar(x, height)` | Bar chart | `plt.bar(['A','B'], [3,5])` | Vertical bars |
| `plt.hist(data)` | Histogram | `plt.hist(np.random.randn(100))` | Distribution plot |
| `plt.title(text)` | Add title | `plt.title('My Plot')` | Chart with title |
| `plt.xlabel(text)` | X-axis label | `plt.xlabel('X values')` | Labeled x-axis |
| `plt.ylabel(text)` | Y-axis label | `plt.ylabel('Y values')` | Labeled y-axis |
| `plt.show()` | Display plot | `plt.show()` | Rendered visualization |
| `plt.savefig(path)` | Save figure | `plt.savefig('plot.png')` | Image file |
| `plt.legend()` | Add legend | `plt.legend(['Line1'])` | Plot with legend |

---
<br><br><br>

## `Intermediate Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `plt.subplots(nrows, ncols)` | Multiple plots | `fig, ax = plt.subplots(2,2)` | Figure with subplots |
| `ax.plot()` | Plot on specific axis | `ax[0,0].plot(x,y)` | Subplot with line |
| `plt.style.use(style)` | Set style | `plt.style.use('ggplot')` | Styled plot |
| `plt.figure(figsize)` | Custom figure size | `plt.figure(figsize=(10,5))` | Larger figure |
| `plt.grid()` | Add grid | `plt.grid(True)` | Plot with grid |
| `plt.tight_layout()` | Adjust spacing | `plt.tight_layout()` | Better subplot spacing |
| `plt.colorbar()` | Add colorbar | `plt.colorbar()` | Color scale bar |
| `plt.xticks(ticks)` | Custom ticks | `plt.xticks([0,1,2])` | Modified x-axis |
| `plt.ylim(min, max)` | Set y-axis limits | `plt.ylim(0,10)` | Fixed y-range |
| `plt.annotate(text, xy)` | Add annotation | `plt.annotate('Peak', (2,4))` | Plot with text |

---
<br><br><br>

## `Advanced Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `fig.add_subplot(projection)` | 3D plots | `ax = fig.add_subplot(111, projection='3d')` | 3D axes |
| `plt.contour(X,Y,Z)` | Contour plot | `plt.contour(X,Y,Z)` | Contour lines |
| `plt.imshow(data)` | Image display | `plt.imshow(np.random.rand(10,10))` | Matrix as image |
| `plt.fill_between(x,y1,y2)` | Fill between lines | `plt.fill_between(x,y1,y2)` | Filled area |
| `plt.errorbar(x,y,yerr)` | Error bars | `plt.errorbar(x,y,yerr=0.2)` | Plot with errors |
| `plt.pcolormesh(X,Y,Z)` | Pseudocolor plot | `plt.pcolormesh(X,Y,Z)` | Colored grid |
| `plt.stem(x,y)` | Stem plot | `plt.stem(x,y)` | Discrete values |
| `plt.boxplot(data)` | Box plot | `plt.boxplot([data1,data2])` | Distribution boxes |
| `plt.pie(sizes)` | Pie chart | `plt.pie([30,70])` | Circular chart |
| `plt.quiver(X,Y,U,V)` | Vector field | `plt.quiver(X,Y,U,V)` | Arrow plot |

---
<br><br><br>

## `Expert Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `matplotlib.animation` | Animated plots | `animation.FuncAnimation(...)` | Moving visualization |
| `mpl_toolkits` | Specialized plots | `from mpl_toolkits.mplot3d import Axes3D` | Advanced 3D |
| `plt.rcParams.update()` | Global styling | `plt.rcParams.update({'font.size':12})` | Custom defaults |
| `matplotlib.widgets` | Interactive widgets | `widgets.Slider(...)` | Interactive plot |
| `plt.gca()` | Current axes | `ax = plt.gca()` | Axes instance |
| `plt.gcf()` | Current figure | `fig = plt.gcf()` | Figure instance |
| `matplotlib.patches` | Custom shapes | `patches.Circle((0,0),1)` | Geometric shapes |
| `plt.text()` | Arbitrary text | `plt.text(0.5,0.5,'Text')` | Custom text |
| `plt.xscale('log')` | Log scale | `plt.xscale('log')` | Logarithmic axis |
| `matplotlib.gridspec` | Complex layouts | `gridspec.GridSpec(2,2)` | Advanced subplots |
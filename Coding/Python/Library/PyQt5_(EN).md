# PyQt5 Functions by Expertise Level

## `Introduction`
**PyQt5** is a comprehensive set of Python bindings for Qt applications:

- ✅ Create desktop GUI applications
- ✅ Cross-platform compatibility
- ✅ Extensive widget library

## `Core Benefits`

| Feature | Explanation |
|---------|-------------|
| ⚡ Native Performance | Direct Qt bindings |
| 🧠 Python Integration | Full Qt functionality in Python |
| 📊 Visualization Tools | Charts, graphs and data visualization |

---
<br><br><br>

## `Beginner Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `QApplication(sys.argv)` | Create application | `app = QApplication(sys.argv)` | Application object |
| `QWidget()` | Base widget | `window = QWidget()` | Empty window |
| `QPushButton(text)` | Create button | `btn = QPushButton('Click')` | Button widget |
| `QLabel(text)` | Create label | `label = QLabel('Hello')` | Text label |
| `QVBoxLayout()` | Vertical layout | `layout = QVBoxLayout()` | Layout manager |
| `QHBoxLayout()` | Horizontal layout | `layout = QHBoxLayout()` | Layout manager |
| `QLineEdit()` | Text input | `input = QLineEdit()` | Text field |
| `show()` | Display widget | `window.show()` | Visible window |
| `exec_()` | Start event loop | `app.exec_()` | Running application |
| `setWindowTitle(text)` | Set window title | `window.setWindowTitle('App')` | Titled window |

---
<br><br><br>

## `Intermediate Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `QMainWindow()` | Main window | `window = QMainWindow()` | Application window |
| `QMessageBox` | Dialog boxes | `QMessageBox.information(None, 'Title', 'Text')` | Popup dialog |
| `QTabWidget()` | Tab interface | `tabs = QTabWidget()` | Tabbed interface |
| `QMenuBar()` | Menu bar | `menubar = window.menuBar()` | Window menu |
| `QStatusBar()` | Status bar | `status = window.statusBar()` | Status display |
| `QAction(text)` | Menu action | `action = QAction('Open')` | Menu item |
| `QFileDialog` | File dialogs | `QFileDialog.getOpenFileName()` | File selector |
| `QTimer()` | Timer | `timer = QTimer()` | Time-based events |
| `QThread()` | Threading | `thread = QThread()` | Background thread |
| `signal.connect(slot)` | Event handling | `btn.clicked.connect(func)` | Button callback |

---
<br><br><br>

## `Advanced Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `QGraphicsView()` | Graphics view | `view = QGraphicsView()` | Canvas for graphics |
| `QGraphicsScene()` | Graphics scene | `scene = QGraphicsScene()` | Graphics container |
| `QPainter()` | Custom painting | `painter = QPainter()` | Drawing interface |
| `QStyledItemDelegate()` | Custom delegates | `class MyDelegate(QStyledItemDelegate)` | Custom item rendering |
| `QAbstractItemModel()` | Data models | `class MyModel(QAbstractItemModel)` | Custom data model |
| `QPropertyAnimation()` | Animations | `anim = QPropertyAnimation(widget, b'pos')` | Widget animation |
| `QWebEngineView()` | Web browser | `web = QWebEngineView()` | Embedded browser |
| `QSplashScreen()` | Splash screen | `splash = QSplashScreen(pixmap)` | Startup screen |
| `QSystemTrayIcon()` | System tray | `tray = QSystemTrayIcon()` | Tray icon |
| `QDataWidgetMapper()` | Data mapping | `mapper = QDataWidgetMapper()` | UI-data binding |

---
<br><br><br>

## `Expert Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `QOpenGLWidget()` | OpenGL widget | `gl = QOpenGLWidget()` | 3D rendering |
| `QPluginLoader()` | Plugin system | `loader = QPluginLoader('plugin.so')` | Loaded plugin |
| `QDBus` | Inter-process | `QDBusConnection.sessionBus()` | D-Bus communication |
| `QStyleFactory` | Custom styles | `app.setStyle(QStyleFactory.create('Fusion'))` | UI styling |
| `QAbstractNativeEventFilter` | System events | `class MyFilter(QAbstractNativeEventFilter)` | OS event handling |
| `QWinTaskbarButton` (Windows) | Taskbar | `taskbtn = QWinTaskbarButton()` | Windows taskbar |
| `QMacToolBar` (Mac) | Toolbar | `toolbar = QMacToolBar()` | macOS toolbar |
| `QtWin` (Windows) | Win32 | `QtWin.setWindowExcludedFromPeek(winId(), True)` | Windows-specific |
| `QGenericArgument` | Meta-object | `QGenericArgument("int", 42)` | Dynamic invocation |
| `QMetaObject` | Reflection | `metaobj = widget.metaObject()` | Introspection |
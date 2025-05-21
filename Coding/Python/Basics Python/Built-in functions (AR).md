<span style="color: #4dd0e1; font-family: 'Segoe UI', Tahoma, sans-serif; font-size: 28px; font-weight: bold; text-shadow: 0 0 5px rgba(77, 208, 225, 0.5);">Built-in Functions</span>

بايثون [`Built-in functions`](https://docs.python.org/3/library/functions.html) هي دوال محددة مسبقًا في اللغة ولا تحتاج إلى استيراد أي مكتبة لاستخدامها. تتوفر هذه الدوال مباشرةً عند تشغيل مترجم بايثون.

| <span style="color:#4dd0e1; font-weight:bold">Category</span> | <span style="color:#4dd0e1; font-weight:bold">Function</span> | <span style="color:#4dd0e1; font-weight:bold">الوصف</span> | <span style="color:#4dd0e1; font-weight:bold">Example</span> | <span style="color:#4dd0e1; font-weight:bold">Result</span> |
|----------|-----------|-------------|---------|--------|
| **A**    | <span style="color:#2962FF">`abs(x)`</span>          | إرجاع القيمة المطلقة لرقم | `abs(-5)`             | `5`                  |
|          | <span style="color:#2962FF">`aiter(async_i)`</span>  | إرجاع مكرر غير متزامن | `aiter(async_iter)`   | `<async_iterator>`   |
|          | <span style="color:#2962FF">`all(iterable)`</span>   | إرجاع `True` إذا كانت كل العناصر صحيحة | `all([1, 1, 1])`      | `True`               |
|          | <span style="color:#2962FF">`anext(async_i)`</span>  | إرجاع العنصر التالي من مكرر غير متزامن | `await anext(async_i)`| `next_value`         |
|          | <span style="color:#2962FF">`any(iterable)`</span>   | إرجاع `True` إذا كان أي عنصر صحيح | `any([0, 1, 0])`      | `True`               |
|          | <span style="color:#2962FF">`ascii(obj)`</span>      | إرجاع تمثيل نصي قابل للطباعة | `ascii('ñ')`          | `"'\\xf1'"`          |
| **B**    | `bin(x)`          | تحويل عدد صحيح إلى سلسلة ثنائية | `bin(3)`              | `'0b11'`             |
|          | `bool(x)`         | تحويل قيمة إلى منطقية | `bool(1)`             | `True`               |
|          | `breakpoint()`    | الدخول إلى المصحح عند نقطة الاستدعاء | `breakpoint()`        | (Enters debugger)    |
|          | `bytearray()`     | إرجاع مصفوفة بايت قابلة للتعديل | `bytearray([65, 66])` | `bytearray(b'AB')`   |
|          | `bytes()`         | إرجاع كائن بايت غير قابل للتعديل | `bytes([65, 66])`     | `b'AB'`              |
| **C**    | `callable(obj)`   | التحقق مما إذا كان الكائن قابل للاستدعاء | `callable(print)`     | `True`               |
|          | `chr(i)`          | إرجاع سلسلة يونيكود لرقم معين | `chr(65)`             | `'A'`                |
|          | `classmethod()`   | تحويل دالة إلى دالة صنف | `@classmethod`        | (Decorator)          |
|          | `compile()`       | تحويل الشفرة المصدرية إلى كائن شفرة | `compile('2+2', ...)` | `<code object>`      |
|          | `complex()`       | إنشاء عدد مركب | `complex(2, 3)`       | `(2+3j)`             |
| **D**    | `delattr(obj, a)` | حذف سمة من كائن | `delattr(obj, 'x')`   | (Attribute removed)  |
|          | `dict()`          | إنشاء قاموس | `dict(a=1, b=2)`      | `{'a': 1, 'b': 2}`   |
|          | `dir()`           | إرجاع قائمة بالأسماء في النطاق الحالي | `dir()`               | `['__builtins__', ...]` |
|          | `divmod(a, b)`    | إرجاع ناتج القسمة والباقي كمجموعة | `divmod(5, 2)`        | `(2, 1)`             |
| **E**    | `enumerate()`     | إرجاع مكرر لأزواج (فهرس، قيمة) | `list(enumerate('ab'))`| `[(0, 'a'), (1, 'b')]` |
|          | `eval()`          | تنفيذ سلسلة كتعبير بايثون | `eval('2+2')`         | `4`                  |
|          | `exec()`          | تنفيذ شفرة بايثون ديناميكية | `exec('x=5')`         | `x = 5`              |
| **F**    | `filter(fn, i)`   | تصفية العناصر التي تعيد الدالة `True` | `list(filter(lambda x: x>0, [-1, 0, 1]))` | `[1]` |
|          | `float(x)`        | تحويل قيمة إلى عدد عشري | `float('3.5')`        | `3.5`                |
|          | `format()`        | تنسيق قيمة إلى سلسلة | `format(3.14159, '.2f')` | `'3.14'`          |
|          | `frozenset()`     | إرجاع مجموعة غير قابلة للتعديل | `frozenset([1, 2, 2])`| `frozenset({1, 2})`  |
| **G**    | `getattr(obj, a)` | الحصول على سمة من كائن | `getattr(obj, 'x')`   | `obj.x`              |
|          | `globals()`       | إرجاع قاموس بالرموز العامة الحالية | `globals()`           | `{...}`              |
| **H**    | `hasattr(obj, a)` | التحقق مما إذا كان الكائن يمتلك سمة | `hasattr(obj, 'x')`   | `True/False`         |
|          | `hash(obj)`       | إرجاع قيمة التجزئة لكائن | `hash('test')`        | `(Unique integer)`   |
|          | `help()`          | استدعاء نظام المساعدة المدمج | `help(print)`         | (Prints help)        |
|          | `hex(x)`          | تحويل عدد صحيح إلى سلسلة ست عشرية | `hex(255)`            | `'0xff'`             |
| **I**    | `id(obj)`         | إرجاع معرف الكائن | `id(obj)`             | `(Unique integer)`   |
|          | `input()`         | قراءة سلسلة من الإدخال القياسي | `input("Name? ")`     | `(User input)`       |
|          | `int(x)`          | تحويل قيمة إلى عدد صحيح | `int('42')`           | `42`                 |
|          | `isinstance(o, c)`| التحقق مما إذا كان الكائن نسخة من صنف | `isinstance(5, int)`  | `True`               |
|          | `issubclass(c, p)`| التحقق مما إذا كان صنف فرعي لآخر | `issubclass(int, object)` | `True`           |
|          | `iter()`          | إرجاع كائن مكرر | `iter([1, 2, 3])`     | `<list_iterator>`    |
| **L**    | `len(s)`          | إرجاع طول كائن | `len('abc')`          | `3`                  |
|          | `list()`          | إنشاء قائمة | `list('abc')`         | `['a', 'b', 'c']`    |
|          | `locals()`        | إرجاع قاموس بالرموز المحلية الحالية | `locals()`            | `{...}`              |
| **M**    | `map(fn, i)`      | تطبيق دالة على كل عنصر في مكرر | `list(map(str.upper, ['a', 'b']))` | `['A', 'B']` |
|          | `max()`           | إرجاع أكبر عنصر | `max([1, 2, 3])`      | `3`                  |
|          | `memoryview()`    | إرجاع كائن عرض للذاكرة | `memoryview(b'abc')`  | `<memoryview>`       |
|          | `min()`           | إرجاع أصغر عنصر | `min([1, 2, 3])`      | `1`                  |
| **N**    | `next(i)`         | استرجاع العنصر التالي من مكرر | `next(iter([1, 2]))`  | `1`                  |
| **O**    | `object()`        | إنشاء كائن أساسي | `object()`            | `<object>`           |
|          | `oct(x)`          | تحويل عدد صحيح إلى سلسلة ثمانية | `oct(8)`              | `'0o10'`             |
|          | `open()`          | فتح ملف وإرجاع كائن ملف | `open('file.txt')`    | `<file object>`      |
|          | `ord(c)`          | إرجاع نقطة كود يونيكود لحرف | `ord('A')`            | `65`                 |
| **P**    | `pow(x, y)`       | إرجاع `x` مرفوعًا لأس `y` | `pow(2, 3)`           | `8`                  |
|          | `print()`         | طباعة كائنات إلى دفق نصي | `print('Hello')`      | `Hello`              |
|          | `property()`      | إرجاع سمة خاصية | `@property`           | (Decorator)          |
| **R**    | `range()`         | توليد سلسلة أرقام | `list(range(3))`      | `[0, 1, 2]`          |
|          | `repr(obj)`       | إرجاع تمثيل نصي للكائن | `repr(3)`             | `'3'`                |
|          | `reversed()`      | إرجاع مكرر عكسي | `list(reversed([1, 2]))` | `[2, 1]`         |
|          | `round()`         | تقريب عدد إلى دقة معينة | `round(3.1415, 2)`    | `3.14`               |
| **S**    | `set()`           | إنشاء مجموعة عناصر فريدة | `set([1, 1, 2])`      | `{1, 2}`             |
|          | `setattr(o, n, v)`| تعيين سمة لكائن | `setattr(obj, 'x', 5)`| `obj.x = 5`          |
|          | `slice()`         | إرجاع كائن مقطع | `slice(1, 5, 2)`      | `slice(1, 5, 2)`     |
|          | `sorted()`        | إرجاع قائمة مرتبة جديدة | `sorted([3, 1, 2])`   | `[1, 2, 3]`          |
|          | `staticmethod()`  | تحويل دالة إلى دالة ثابتة | `@staticmethod`       | (Decorator)          |
|          | `str()`           | إرجاع نسخة نصية للكائن | `str(3.14)`           | `'3.14'`             |
|          | `sum()`           | جمع عناصر مكرر | `sum([1, 2, 3])`      | `6`                  |
|          | `super()`         | إرجاع وكيل لفئة الأب | `super().__init__()`  | (Parent method call) |
| **T**    | `tuple()`         | إنشاء سلسلة غير قابلة للتعديل | `tuple([1, 2, 3])`    | `(1, 2, 3)`          |
|          | `type()`          | إرجاع نوع الكائن | `type(3)`             | `<class 'int'>`      |
| **V**    | `vars()`          | إرجاع `__dict__` للكائن | `vars(obj)`           | `obj.__dict__`       |
| **Z**    | `zip()`           | تجميع العناصر من كل مكرر | `list(zip([1, 2], ['a', 'b']))` | `[(1, 'a'), (2, 'b')]` |
| **_**    | `__import__()`    | الدالة المستدعاة ببيان `import` | `__import__('math')`  | `<module 'math'>`    |
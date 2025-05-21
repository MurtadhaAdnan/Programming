# `Numerical Operators`

| Operator | Description                      | Example          | Result       |
|----------|----------------------------|------------------|--------------|
| `+`      | جمع                        | `3 + 2`          | `5`          |
| `-`      | طرح                        | `5 - 2`          | `3`          |
| `*`      | ضرب                        | `3 * 4`          | `12`         |
| `/`      | قسمة                       | `10 / 2`         | `5.0`        |
| `**`     | أس                         | `2 ** 3`         | `8`          |
| `//`     | قسمة صحيحة                 | `7 // 2`         | `3`          |
| `%`      | باقي القسمة                | `7 % 3`          | `1`          |

---

# `Comparison Operators`

| Operator | Description                      | Example          | Result       |
|----------|----------------------------|------------------|--------------|
| `<`      | أصغر من                   | `3 < 5`          | `True`       |
| `<=`     | أصغر من أو يساوي           | `5 <= 5`         | `True`       |
| `>`      | أكبر من                    | `7 > 3`          | `True`       |
| `>=`     | أكبر من أو يساوي           | `4 >= 4`         | `True`       |
| `==`     | يساوي                      | `'a' == 'a'`     | `True`       |
| `!=`     | لا يساوي                   | `2 != 3`         | `True`       |

---

# `Python Keywords Classification`

| Category            | Keyword    | Description                      | Example                  | Result/Usage               |
|---------------------|------------|----------------------------|--------------------------|--------------------------|
| **Module Management** | `import`   | استيراد وحدة               | `import math`            | Imports math module        |
|                     | `from`     | استيراد عناصر محددة        | `from math import sqrt`  | Imports sqrt function      |
|                     | `as`       | إنشاء اسم مستعار           | `import numpy as np`     | Creates np alias           |
| **Conditionals**     | `if`       | تنفيذ شرطي                 | `if x > 0: print(x)`     | Runs if condition is True  |
|                     | `elif`     | شرط ثانوي                  | `elif x < 0: print(x)`   | Alternative condition      |
|                     | `else`     | الحالة الافتراضية          | `else: print(0)`         | Runs if all else fails     |
| **Loops**           | `for`      | تكرار عبر متسلسلة          | `for i in range(3):`     | Loops 3 times (0,1,2)      |
|                     | `while`    | تكرار طالما الشرط صحيح     | `while x < 5: x+=1`      | Loops until x >= 5         |
|                     | `break`    | إيقاف الحلقة               | `while True: break`      | Exits after first iteration|
|                     | `continue` | تخطي التكرار الحالي        | `for i in range(3):`<br>`&nbsp;&nbsp;if i==1: continue` | Skips i=1 |
|                     | `pass`     | أمر فارغ                   | `def f(): pass`          | Empty function definition  |
| **Functions & Classes** | `def`    | تعريف دالة                 | `def f(x): return x+1`   | Creates function f         |
|                     | `lambda`   | دالة مجهولة               | `f = lambda x: x*2`      | Creates one-line function  |
|                     | `class`    | تعريف صنف                  | `class MyClass:`         | Creates new class          |
|                     | `return`   | إرجاع قيمة من الدالة       | `return x`               | Returns value from func    |
|                     | `yield`    | إرجاع من المولد            | `def f(): yield 1`       | Creates generator          |
| **Exception Handling** | `try`    | محاولة تنفيذ كود           | `try: 1/0`              | Attempts division          |
|                     | `except`   | معالجة الاستثناءات         | `except: print("Error")`| Catches any exception      |
|                     | `finally`  | تنفيذ كود نهائي            | `finally: print("Done")`| Runs after try/except      |
|                     | `raise`    | رفع استثناء                | `raise ValueError()`    | Raises specific error      |
|                     | `assert`   | التحقق من صحة شرط          | `assert x > 0`          | Raises AssertionError if False |
| **Scope Management** | `global`   | متغير عام                  | `global x`              | Modifies global x          |
|                     | `nonlocal` | متغير من النطاق الخارجي    | `nonlocal x`            | Modifies outer function's x|
| **Boolean & Special Values** | `True` | قيمة منطقية صحيحة         | `x = True`              | Assigns True               |
|                     | `False`    | قيمة منطقية خاطئة          | `y = False`             | Assigns False              |
|                     | `None`     | قيمة فارغة                 | `z = None`              | Assigns null value         |
| **Logical Operators** | `and`    | AND منطقي                  | `True and False`        | `False`                    |
|                     | `or`       | OR منطقي                   | `True or False`        | `True`                     |
|                     | `not`      | NOT منطقي                  | `not True`             | `False`                    |
| **Membership & Identity** | `in` | اختبار العضوية             | `'a' in 'abc'`         | `True`                     |
|                     | `is`       | اختبار الهوية              | `x is None`            | Checks if x is None        |
| **Context Managers** | `with`     | مدير السياق                | `with open('f.txt') as f:` | Auto-closes file        |
|                     | `del`      | حذف كائن                   | `del x`                 | Removes variable x         |

# `Complete Python Keywords`

| Keyword    | Description                      | Example                  | Result/Usage               |
|------------|----------------------------|--------------------------|--------------------------|
| `and`      | AND منطقي                  | `True and False`         | `False`                    |
| `as`       | إنشاء اسم مستعار           | `import math as m`       | Creates alias 'm'          |
| `assert`   | تأكيد صحة شرط              | `assert 1 == 1`          | Does nothing if True       |
| `break`    | كسر الحلقة                 | `while True: break`      | Exits loop                 |
| `class`    | تعريف صنف                  | `class MyClass: pass`    | Creates empty class        |
| `continue` | متابعة التكرار التالي       | `for i in range(3):`<br>`&nbsp;&nbsp;if i==1: continue` | Skips when i=1 |
| `def`      | تعريف دالة                 | `def f(): return 1`      | Creates function f         |
| `del`      | حذف كائن                   | `del x`                  | Removes variable x         |
| `elif`     | شرط ثانوي                  | `if x>0:`<br>`elif x<0:` | Alternative condition      |
| `else`     | شرط افتراضي                | `if x>0:`<br>`else:`     | Final case                 |
| `except`   | معالجة الاستثناء           | `try:`<br>`except:`      | Catches exceptions         |
| `False`    | قيمة منطقية خاطئة          | `x = False`              | Assigns False              |
| `finally`  | كود تنفيذ نهائي            | `try:`<br>`finally:`     | Always executes            |
| `for`      | حلقة تكرار                 | `for x in range(3):`     | Loops 3 times              |
| `from`     | استيراد من وحدة            | `from math import sqrt`  | Imports sqrt function      |
| `global`   | متغير عام                  | `global x`               | Accesses global x          |
| `if`       | شرط                        | `if x > 0:`              | Conditional execution      |
| `import`   | استيراد وحدة               | `import os`              | Imports OS module          |
| `in`       | اختبار وجود                | `'a' in 'abc'`           | `True`                     |
| `is`       | اختبار هوية                | `x is None`              | Checks if x is None        |
| `lambda`   | دالة مجهولة               | `f = lambda x: x+1`      | Creates one-line function  |
| `None`     | قيمة فارغة                 | `x = None`               | Assigns null               |
| `nonlocal` | متغير من نطاق خارجي        | `nonlocal x`             | Modifies enclosing scope   |
| `not`      | NOT منطقي                  | `not True`               | `False`                    |
| `or`       | OR منطقي                   | `True or False`          | `True`                     |
| `pass`     | أمر فارغ                   | `def f(): pass`          | Empty function             |
| `raise`    | رفع استثناء                | `raise ValueError()`     | Raises error               |
| `return`   | إرجاع قيمة                 | `def f(): return 1`      | Returns 1                  |
| `True`     | قيمة منطقية صحيحة          | `x = True`               | Assigns True               |
| `try`      | محاولة تنفيذ               | `try: 1/0`               | Attempts operation         |
| `while`    | حلقة شرطية                 | `while x < 3:`           | Loops while condition True |
| `with`     | مدير سياق                  | `with open('f') as f:`   | Auto-closes file           |
| `yield`    | إرجاع من مولد              | `def f(): yield 1`       | Creates generator          |
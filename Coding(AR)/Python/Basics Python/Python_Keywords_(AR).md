# `Numerical Operators`

| # | Operator | Description      | Example    | Result   |
|---|----------|------------------|------------|----------|
| 1 | `+`      | جمع             | `3 + 2`    | `5`      |
| 2 | `-`      | طرح             | `5 - 2`    | `3`      |
| 3 | `*`      | ضرب             | `3 * 4`    | `12`     |
| 4 | `/`      | قسمة            | `10 / 2`   | `5.0`    |
| 5 | `**`     | أس              | `2 ** 3`   | `8`      |
| 6 | `//`     | قسمة صحيحة      | `7 // 2`   | `3`      |
| 7 | `%`      | باقي القسمة     | `7 % 3`    | `1`      |

---

# `Comparison Operators`

| # | Operator | Description              | Example      | Result   |
|---|----------|--------------------------|--------------|----------|
| 1 | `<`      | أصغر من                 | `3 < 5`      | `True`   |
| 2 | `<=`     | أصغر من أو يساوي         | `5 <= 5`     | `True`   |
| 3 | `>`      | أكبر من                  | `7 > 3`      | `True`   |
| 4 | `>=`     | أكبر من أو يساوي         | `4 >= 4`     | `True`   |
| 5 | `==`     | يساوي                    | `'a' == 'a'` | `True`   |
| 6 | `!=`     | لا يساوي                 | `2 != 3`     | `True`   |

---

# `Python Keywords Classification`

| # | Category                 | Keyword    | Description                      | Example                  | Result/Usage               |
|---|--------------------------|------------|----------------------------------|--------------------------|----------------------------|
| 1 | **Module Management**    | `import`   | استيراد وحدة                   | `import math`            | Imports math module        |
| 2 |                          | `from`     | استيراد عناصر محددة            | `from math import sqrt`  | Imports sqrt function      |
| 3 |                          | `as`       | إنشاء اسم مستعار               | `import numpy as np`     | Creates np alias           |
| 4 | **Asynchronous**         | `async`    | تعريف دالة/سياق غير متزامن     | `async def f():`         | Creates coroutine function |
| 5 |                          | `await`    | انتظار نتيجة غير متزامنة       | `await some_task()`      | Waits for async operation  |
| 6 | **Conditionals**         | `if`       | تنفيذ شرطي                     | `if x > 0: print(x)`     | Runs if condition is True  |
| 7 |                          | `elif`     | شرط ثانوي                      | `elif x < 0: print(x)`   | Alternative condition      |
| 8 |                          | `else`     | الحالة الافتراضية              | `else: print(0)`         | Runs if all else fails     |
| 9 | **Loops**               | `for`      | تكرار عبر متسلسلة              | `for i in range(3):`     | Loops 3 times (0,1,2)      |
|10 |                          | `while`    | تكرار طالما الشرط صحيح         | `while x < 5: x+=1`      | Loops until x >= 5         |
|11 |                          | `break`    | إيقاف الحلقة                   | `while True: break`      | Exits after first iteration|
|12 |                          | `continue` | تخطي التكرار الحالي            | `for i in range(3):`<br>`&nbsp;&nbsp;if i==1: continue` | Skips i=1 |
|13 |                          | `pass`     | أمر فارغ                       | `def f(): pass`          | Empty function definition  |
|14 | **Functions & Classes** | `def`      | تعريف دالة                     | `def f(x): return x+1`   | Creates function f         |
|15 |                          | `lambda`   | دالة مجهولة                   | `f = lambda x: x*2`      | Creates one-line function  |
|16 |                          | `class`    | تعريف صنف                      | `class MyClass:`         | Creates new class          |
|17 |                          | `return`   | إرجاع قيمة من الدالة           | `return x`               | Returns value from func    |
|18 |                          | `yield`    | إرجاع من المولد                | `def f(): yield 1`       | Creates generator          |
|19 | **Exception Handling**  | `try`      | محاولة تنفيذ كود               | `try: 1/0`              | Attempts division          |
|20 |                          | `except`   | معالجة الاستثناءات             | `except: print("Error")`| Catches any exception      |
|21 |                          | `finally`  | تنفيذ كود نهائي                | `finally: print("Done")`| Runs after try/except      |
|22 |                          | `raise`    | رفع استثناء                    | `raise ValueError()`    | Raises specific error      |
|23 |                          | `assert`   | التحقق من صحة شرط              | `assert x > 0`          | Raises AssertionError if False |
|24 | **Scope Management**    | `global`   | متغير عام                      | `global x`              | Modifies global x          |
|25 |                          | `nonlocal` | متغير من النطاق الخارجي        | `nonlocal x`            | Modifies outer function's x|
|26 | **Boolean & Values**    | `True`     | قيمة منطقية صحيحة              | `x = True`              | Assigns True               |
|27 |                          | `False`    | قيمة منطقية خاطئة              | `y = False`             | Assigns False              |
|28 |                          | `None`     | قيمة فارغة                     | `z = None`              | Assigns null value         |
|29 | **Logical Operators**   | `and`      | AND منطقي                      | `True and False`        | `False`                    |
|30 |                          | `or`       | OR منطقي                       | `True or False`        | `True`                     |
|31 |                          | `not`      | NOT منطقي                      | `not True`             | `False`                    |
|32 | **Membership & Identity** | `in`    | اختبار العضوية                 | `'a' in 'abc'`         | `True`                     |
|33 |                          | `is`       | اختبار الهوية                  | `x is None`            | Checks if x is None        |
|34 | **Context Managers**    | `with`     | مدير السياق                    | `with open('f.txt') as f:` | Auto-closes file        |
|35 |                          | `del`      | حذف كائن                       | `del x`                 | Removes variable x         |

---

# `Complete Python Keywords`

| # | Keyword    | Description                      | Example                  | Result/Usage               |
|---|------------|----------------------------------|--------------------------|----------------------------|
| 1 | `and`      | AND منطقي                       | `True and False`         | `False`                    |
| 2 | `as`       | إنشاء اسم مستعار                | `import math as m`       | Creates alias 'm'          |
| 3 | `assert`   | تأكيد صحة شرط                   | `assert 1 == 1`          | Does nothing if True       |
| 4 | `async`    | تعريف دالة/سياق غير متزامن      | `async def f():`         | Creates coroutine function |
| 5 | `await`    | انتظار نتيجة غير متزامنة        | `await some_task()`      | Waits for async operation  |
| 6 | `break`    | كسر الحلقة                      | `while True: break`      | Exits loop                 |
| 7 | `class`    | تعريف صنف                       | `class MyClass: pass`    | Creates empty class        |
| 8 | `continue` | متابعة التكرار التالي            | `for i in range(3):`<br>`&nbsp;&nbsp;if i==1: continue` | Skips when i=1 |
| 9 | `def`      | تعريف دالة                      | `def f(): return 1`      | Creates function f         |
|10 | `del`      | حذف كائن                        | `del x`                  | Removes variable x         |
|11 | `elif`     | شرط ثانوي                       | `if x>0:`<br>`elif x<0:` | Alternative condition      |
|12 | `else`     | شرط افتراضي                     | `if x>0:`<br>`else:`     | Final case                 |
|13 | `except`   | معالجة الاستثناء                | `try:`<br>`except:`      | Catches exceptions         |
|14 | `False`    | قيمة منطقية خاطئة               | `x = False`              | Assigns False              |
|15 | `finally`  | كود تنفيذ نهائي                 | `try:`<br>`finally:`     | Always executes            |
|16 | `for`      | حلقة تكرار                      | `for x in range(3):`     | Loops 3 times              |
|17 | `from`     | استيراد من وحدة                 | `from math import sqrt`  | Imports sqrt function      |
|18 | `global`   | متغير عام                       | `global x`               | Accesses global x          |
|19 | `if`       | شرط                             | `if x > 0:`              | Conditional execution      |
|20 | `import`   | استيراد وحدة                    | `import os`              | Imports OS module          |
|21 | `in`       | اختبار وجود                     | `'a' in 'abc'`           | `True`                     |
|22 | `is`       | اختبار هوية                     | `x is None`              | Checks if x is None        |
|23 | `lambda`   | دالة مجهولة                    | `f = lambda x: x+1`      | Creates one-line function  |
|24 | `None`     | قيمة فارغة                      | `x = None`               | Assigns null               |
|25 | `nonlocal` | متغير من نطاق خارجي             | `nonlocal x`             | Modifies enclosing scope   |
|26 | `not`      | NOT منطقي                       | `not True`               | `False`                    |
|27 | `or`       | OR منطقي                        | `True or False`          | `True`                     |
|28 | `pass`     | أمر فارغ                        | `def f(): pass`          | Empty function             |
|29 | `raise`    | رفع استثناء                     | `raise ValueError()`     | Raises error               |
|30 | `return`   | إرجاع قيمة                      | `def f(): return 1`      | Returns 1                  |
|31 | `True`     | قيمة منطقية صحيحة               | `x = True`               | Assigns True               |
|32 | `try`      | محاولة تنفيذ                    | `try: 1/0`               | Attempts operation         |
|33 | `while`    | حلقة شرطية                      | `while x < 3:`           | Loops while condition True |
|34 | `with`     | مدير سياق                       | `with open('f') as f:`   | Auto-closes file           |
|35 | `yield`    | إرجاع من مولد                   | `def f(): yield 1`       | Creates generator          |

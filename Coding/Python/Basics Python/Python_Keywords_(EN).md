# `Numerical Operators`

| Operator | Description          | Example          | Result       |
|----------|----------------------|------------------|--------------|
| `+`      | Addition             | `3 + 2`          | `5`          |
| `-`      | Subtraction          | `5 - 2`          | `3`          |
| `*`      | Multiplication       | `3 * 4`          | `12`         |
| `/`      | Division             | `10 / 2`         | `5.0`        |
| `**`     | Exponentiation       | `2 ** 3`         | `8`          |
| `//`     | Floor Division       | `7 // 2`         | `3`          |
| `%`      | Modulus (Remainder)  | `7 % 3`          | `1`          |

---

# `Comparison Operators`

| Operator | Description          | Example          | Result       |
|----------|----------------------|------------------|--------------|
| `<`      | Less than            | `3 < 5`          | `True`       |
| `<=`     | Less than or equal   | `5 <= 5`         | `True`       |
| `>`      | Greater than         | `7 > 3`          | `True`       |
| `>=`     | Greater than or equal| `4 >= 4`         | `True`       |
| `==`     | Equal to             | `'a' == 'a'`     | `True`       |
| `!=`     | Not equal to         | `2 != 3`         | `True`       |

---

# `Python Keywords Classification`

| Category            | Keyword    | Description                  | Example                  | Result/Usage               |
|---------------------|------------|------------------------------|--------------------------|----------------------------|
| **Module Management** | `import`   | Import a module              | `import math`            | Imports math module        |
|                     | `from`     | Import specific items        | `from math import sqrt`  | Imports sqrt function      |
|                     | `as`       | Create an alias              | `import numpy as np`     | Creates np alias           |
| **Conditionals**     | `if`       | Conditional execution        | `if x > 0: print(x)`     | Runs if condition is True  |
|                     | `elif`     | Else if condition            | `elif x < 0: print(x)`   | Alternative condition      |
|                     | `else`     | Final condition case         | `else: print(0)`         | Runs if all else fails     |
| **Loops**           | `for`      | Iterate over sequence        | `for i in range(3):`     | Loops 3 times (0,1,2)      |
|                     | `while`    | Loop while condition is True | `while x < 5: x+=1`      | Loops until x >= 5         |
|                     | `break`    | Exit loop immediately        | `while True: break`      | Exits after first iteration|
|                     | `continue` | Skip to next iteration       | `for i in range(3):`<br>`&nbsp;&nbsp;if i==1: continue` | Skips i=1 |
|                     | `pass`     | Placeholder for empty block  | `def f(): pass`          | Empty function definition  |
| **Functions & Classes** | `def`    | Define a function            | `def f(x): return x+1`   | Creates function f         |
|                     | `lambda`   | Anonymous function           | `f = lambda x: x*2`      | Creates one-line function  |
|                     | `class`    | Define a class               | `class MyClass:`         | Creates new class          |
|                     | `return`   | Return from function         | `return x`               | Returns value from func    |
|                     | `yield`    | Generator function           | `def f(): yield 1`       | Creates generator          |
| **Exception Handling** | `try`    | Attempt risky code           | `try: 1/0`              | Attempts division          |
|                     | `except`   | Handle exceptions            | `except: print("Error")`| Catches any exception      |
|                     | `finally`  | Always execute code          | `finally: print("Done")`| Runs after try/except      |
|                     | `raise`    | Raise an exception           | `raise ValueError()`    | Raises specific error      |
|                     | `assert`   | Debug assertion              | `assert x > 0`          | Raises AssertionError if False |
| **Scope Management** | `global`   | Access global variable       | `global x`              | Modifies global x          |
|                     | `nonlocal` | Access enclosing scope       | `nonlocal x`            | Modifies outer function's x|
| **Boolean & Special Values** | `True` | Boolean true value           | `x = True`              | Assigns True               |
|                     | `False`    | Boolean false value          | `y = False`             | Assigns False              |
|                     | `None`     | Null/absent value            | `z = None`              | Assigns null value         |
| **Logical Operators** | `and`    | Logical AND                  | `True and False`        | `False`                    |
|                     | `or`       | Logical OR                   | `True or False`        | `True`                     |
|                     | `not`      | Logical NOT                  | `not True`             | `False`                    |
| **Membership & Identity** | `in` | Membership test              | `'a' in 'abc'`         | `True`                     |
|                     | `is`       | Identity comparison          | `x is None`            | Checks if x is None        |
| **Context Managers** | `with`     | Resource management          | `with open('f.txt') as f:` | Auto-closes file        |
|                     | `del`      | Delete reference             | `del x`                 | Removes variable x         |
# `Complete Python Keywords`

| Keyword    | Description                  | Example                  | Result/Usage               |
|------------|------------------------------|--------------------------|----------------------------|
| `and`      | Logical AND                  | `True and False`         | `False`                    |
| `as`       | Alias creation               | `import math as m`       | Creates alias 'm'          |
| `assert`   | Debug assertion              | `assert 1 == 1`          | Does nothing if True       |
| `break`    | Exit loop                    | `while True: break`      | Exits loop                 |
| `class`    | Define class                 | `class MyClass: pass`    | Creates empty class        |
| `continue` | Skip to next iteration       | `for i in range(3):`<br>`&nbsp;&nbsp;if i==1: continue` | Skips when i=1 |
| `def`      | Define function              | `def f(): return 1`      | Creates function f         |
| `del`      | Delete object                | `del x`                  | Removes variable x         |
| `elif`     | Else if condition            | `if x>0:`<br>`elif x<0:` | Alternative condition      |
| `else`     | Final condition              | `if x>0:`<br>`else:`     | Final case                 |
| `except`   | Handle exceptions            | `try:`<br>`except:`      | Catches exceptions         |
| `False`    | Boolean false                | `x = False`              | Assigns False              |
| `finally`  | Cleanup after try/except     | `try:`<br>`finally:`     | Always executes            |
| `for`      | For loop                     | `for x in range(3):`     | Loops 3 times              |
| `from`     | Import specific items        | `from math import sqrt`  | Imports sqrt function      |
| `global`   | Declare global variable      | `global x`               | Accesses global x          |
| `if`       | Conditional                  | `if x > 0:`              | Conditional execution      |
| `import`   | Import module                | `import os`              | Imports OS module          |
| `in`       | Membership test              | `'a' in 'abc'`           | `True`                     |
| `is`       | Identity test                | `x is None`              | Checks if x is None        |
| `lambda`   | Anonymous function           | `f = lambda x: x+1`      | Creates one-line function  |
| `None`     | Null value                   | `x = None`               | Assigns null               |
| `nonlocal` | Access outer scope variable  | `nonlocal x`             | Modifies enclosing scope   |
| `not`      | Logical NOT                  | `not True`               | `False`                    |
| `or`       | Logical OR                   | `True or False`          | `True`                     |
| `pass`     | Do nothing                   | `def f(): pass`          | Empty function             |
| `raise`    | Raise exception              | `raise ValueError()`     | Raises error               |
| `return`   | Return from function         | `def f(): return 1`      | Returns 1                  |
| `True`     | Boolean true                 | `x = True`               | Assigns True               |
| `try`      | Exception handling block     | `try: 1/0`               | Attempts operation         |
| `while`    | While loop                   | `while x < 3:`           | Loops while condition True |
| `with`     | Context manager              | `with open('f') as f:`   | Auto-closes file           |
| `yield`    | Generator return             | `def f(): yield 1`       | Creates generator          |
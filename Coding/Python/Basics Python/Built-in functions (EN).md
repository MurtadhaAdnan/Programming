# Built-in functions

Python [`Built-in functions`](https://docs.python.org/3/library/functions.html) are predefined functions in the language and you don't need to import any library to use them. These functions are available directly when you run the Python interpreter.
-




| <span style="color:#4dd0e1; font-weight:bold">Category</span> | <span style="color:#4dd0e1; font-weight:bold">Function</span> | <span style="color:#4dd0e1; font-weight:bold">Description</span> | <span style="color:#4dd0e1; font-weight:bold">Example</span> | <span style="color:#4dd0e1; font-weight:bold">Result</span> |
|----------|-----------|-------------|---------|--------|
| **A**    | `abs(x)`          | Returns the absolute value of a number                                      | `abs(-5)`             | `5`                  |
|          | `aiter(async_i)`  | Returns an asynchronous iterator                                            | `aiter(async_iter)`   | `<async_iterator>`   |
|          | `all(iterable)`   | Returns `True` if all elements are truthy                                   | `all([1, 1, 1])`      | `True`               |
|          | `anext(async_i)`  | Returns the next item from an async iterator                                | `await anext(async_i)`| `next_value`         |
|          | `any(iterable)`   | Returns `True` if any element is truthy                                     | `any([0, 1, 0])`      | `True`               |
|          | `ascii(obj)`      | Returns a string containing a printable representation                      | `ascii('ñ')`          | `"'\\xf1'"`          |
| **B**    | `bin(x)`          | Converts an integer to a binary string                                      | `bin(3)`              | `'0b11'`             |
|          | `bool(x)`         | Converts a value to a boolean                                               | `bool(1)`             | `True`               |
|          | `breakpoint()`    | Drops into the debugger at the call site                                    | `breakpoint()`        | (Enters debugger)    |
|          | `bytearray()`     | Returns a mutable array of bytes                                            | `bytearray([65, 66])` | `bytearray(b'AB')`   |
|          | `bytes()`         | Returns an immutable bytes object                                           | `bytes([65, 66])`     | `b'AB'`              |
| **C**    | `callable(obj)`   | Checks if an object is callable                                             | `callable(print)`     | `True`               |
|          | `chr(i)`          | Returns a Unicode string for an integer (0-0x10FFFF)                        | `chr(65)`             | `'A'`                |
|          | `classmethod()`   | Converts a function to a class method                                       | `@classmethod`        | (Decorator)          |
|          | `compile()`       | Compiles source into a code object                                          | `compile('2+2', ...)` | `<code object>`      |
|          | `complex()`       | Creates a complex number                                                    | `complex(2, 3)`       | `(2+3j)`             |
| **D**    | `delattr(obj, a)` | Deletes an attribute from an object                                         | `delattr(obj, 'x')`   | (Attribute removed)  |
|          | `dict()`          | Creates a dictionary                                                        | `dict(a=1, b=2)`      | `{'a': 1, 'b': 2}`   |
|          | `dir()`           | Returns a list of names in the current scope                                | `dir()`               | `['__builtins__', ...]` |
|          | `divmod(a, b)`    | Returns quotient and remainder as a tuple                                   | `divmod(5, 2)`        | `(2, 1)`             |
| **E**    | `enumerate()`     | Returns an iterator of (index, value) pairs                                 | `list(enumerate('ab'))`| `[(0, 'a'), (1, 'b')]` |
|          | `eval()`          | Evaluates a string as a Python expression                                   | `eval('2+2')`         | `4`                  |
|          | `exec()`          | Executes dynamically created Python code                                    | `exec('x=5')`         | `x = 5`              |
| **F**    | `filter(fn, i)`   | Filters elements where the function returns `True`                          | `list(filter(lambda x: x>0, [-1, 0, 1]))` | `[1]` |
|          | `float(x)`        | Converts a value to a floating-point number                                 | `float('3.5')`        | `3.5`                |
|          | `format()`        | Formats a value into a string                                               | `format(3.14159, '.2f')` | `'3.14'`          |
|          | `frozenset()`     | Returns an immutable set                                                    | `frozenset([1, 2, 2])`| `frozenset({1, 2})`  |
| **G**    | `getattr(obj, a)` | Gets a named attribute of an object                                         | `getattr(obj, 'x')`   | `obj.x`              |
|          | `globals()`       | Returns a dictionary of the current global symbol table                     | `globals()`           | `{...}`              |
| **H**    | `hasattr(obj, a)` | Checks if an object has an attribute                                        | `hasattr(obj, 'x')`   | `True/False`         |
|          | `hash(obj)`       | Returns the hash value of an object                                         | `hash('test')`        | `(Unique integer)`   |
|          | `help()`          | Invokes the built-in help system                                            | `help(print)`         | (Prints help)        |
|          | `hex(x)`          | Converts an integer to a hexadecimal string                                 | `hex(255)`            | `'0xff'`             |
| **I**    | `id(obj)`         | Returns the identity of an object                                           | `id(obj)`             | `(Unique integer)`   |
|          | `input()`         | Reads a string from standard input                                          | `input("Name? ")`     | `(User input)`       |
|          | `int(x)`          | Converts a value to an integer                                              | `int('42')`           | `42`                 |
|          | `isinstance(o, c)`| Checks if an object is an instance of a class                               | `isinstance(5, int)`  | `True`               |
|          | `issubclass(c, p)`| Checks if a class is a subclass of another                                  | `issubclass(int, object)` | `True`           |
|          | `iter()`          | Returns an iterator object                                                  | `iter([1, 2, 3])`     | `<list_iterator>`    |
| **L**    | `len(s)`          | Returns the length of an object                                             | `len('abc')`          | `3`                  |
|          | `list()`          | Creates a list                                                              | `list('abc')`         | `['a', 'b', 'c']`    |
|          | `locals()`        | Returns a dictionary of the current local symbol table                      | `locals()`            | `{...}`              |
| **M**    | `map(fn, i)`      | Applies a function to every item of an iterable                             | `list(map(str.upper, ['a', 'b']))` | `['A', 'B']` |
|          | `max()`           | Returns the largest item                                                    | `max([1, 2, 3])`      | `3`                  |
|          | `memoryview()`    | Returns a memory view object                                                | `memoryview(b'abc')`  | `<memoryview>`       |
|          | `min()`           | Returns the smallest item                                                   | `min([1, 2, 3])`      | `1`                  |
| **N**    | `next(i)`         | Retrieves the next item from an iterator                                    | `next(iter([1, 2]))`  | `1`                  |
| **O**    | `object()`        | Creates a base object                                                       | `object()`            | `<object>`           |
|          | `oct(x)`          | Converts an integer to an octal string                                      | `oct(8)`              | `'0o10'`             |
|          | `open()`          | Opens a file and returns a file object                                      | `open('file.txt')`    | `<file object>`      |
|          | `ord(c)`          | Returns the Unicode code point for a character                              | `ord('A')`            | `65`                 |
| **P**    | `pow(x, y)`       | Returns `x` to the power of `y`                                             | `pow(2, 3)`           | `8`                  |
|          | `print()`         | Prints objects to a text stream                                             | `print('Hello')`      | `Hello`              |
|          | `property()`      | Returns a property attribute                                                | `@property`           | (Decorator)          |
| **R**    | `range()`         | Generates a sequence of numbers                                             | `list(range(3))`      | `[0, 1, 2]`          |
|          | `repr(obj)`       | Returns a string representation of an object                                | `repr(3)`             | `'3'`                |
|          | `reversed()`      | Returns a reverse iterator                                                  | `list(reversed([1, 2]))` | `[2, 1]`         |
|          | `round()`         | Rounds a number to a given precision                                        | `round(3.1415, 2)`    | `3.14`               |
| **S**    | `set()`           | Creates an unordered collection of unique elements                          | `set([1, 1, 2])`      | `{1, 2}`             |
|          | `setattr(o, n, v)`| Sets an attribute of an object                                              | `setattr(obj, 'x', 5)`| `obj.x = 5`          |
|          | `slice()`         | Returns a slice object                                                      | `slice(1, 5, 2)`      | `slice(1, 5, 2)`     |
|          | `sorted()`        | Returns a new sorted list                                                   | `sorted([3, 1, 2])`   | `[1, 2, 3]`          |
|          | `staticmethod()`  | Converts a function to a static method                                      | `@staticmethod`       | (Decorator)          |
|          | `str()`           | Returns a string version of an object                                       | `str(3.14)`           | `'3.14'`             |
|          | `sum()`           | Sums the items of an iterable                                               | `sum([1, 2, 3])`      | `6`                  |
|          | `super()`         | Returns a proxy object for parent class delegation                          | `super().__init__()`  | (Parent method call) |
| **T**    | `tuple()`         | Creates an immutable sequence                                               | `tuple([1, 2, 3])`    | `(1, 2, 3)`          |
|          | `type()`          | Returns the type of an object                                               | `type(3)`             | `<class 'int'>`      |
| **V**    | `vars()`          | Returns the `__dict__` of an object                                         | `vars(obj)`           | `obj.__dict__`       |
| **Z**    | `zip()`           | Aggregates elements from each iterable                                      | `list(zip([1, 2], ['a', 'b']))` | `[(1, 'a'), (2, 'b')]` |
| **_**    | `__import__()`    | Function called by the `import` statement                                   | `__import__('math')`  | `<module 'math'>`    |

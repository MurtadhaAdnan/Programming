# `Python Methods `

# `List Methods`

| Method          | Description                              | Example                     | Result             |
|-----------------|------------------------------------------|-----------------------------|--------------------|
| `append(x)`     | Adds item to end of list                 | `lst = [1,2]; lst.append(3)`| `[1, 2, 3]`        |
| `clear()`       | Removes all elements                     | `lst = [1,2]; lst.clear()`  | `[]`               |
| `copy()`        | Returns shallow copy                     | `lst = [1,2]; lst.copy()`   | `[1, 2]`           |
| `count(x)`      | Returns occurrences of x                 | `[1,1,2].count(1)`          | `2`                |
| `extend(iter)`  | Extends list with iterable               | `[1,2].extend([3,4])`       | `[1, 2, 3, 4]`     |
| `index(x)`      | Returns first index of x                 | `['a','b'].index('b')`      | `1`                |
| `insert(i,x)`   | Inserts x at position i                  | `[1,3].insert(1,2)`         | `[1, 2, 3]`        |
| `pop([i])`      | Removes and returns item at i (last if omitted) | `[1,2,3].pop(1)` | `2` (list becomes `[1, 3]`) |
| `remove(x)`     | Removes first occurrence of x            | `[1,2,1].remove(1)`         | `[2, 1]`           |
| `reverse()`     | Reverses elements in place               | `[1,2].reverse()`           | `[2, 1]`           |
| `sort()`        | Sorts list in ascending order            | `[3,1,2].sort()`            | `[1, 2, 3]`        |

#  `Dictionary Methods`

| Method          | Description                              | Example                     | Result             |
|-----------------|------------------------------------------|-----------------------------|--------------------|
| `clear()`       | Removes all items                        | `d = {'a':1}; d.clear()`    | `{}`               |
| `copy()`        | Returns shallow copy                     | `d = {'a':1}; d.copy()`     | `{'a':1}`          |
| `fromkeys(seq)` | Creates new dict with keys from sequence | `dict.fromkeys(['a','b'])`  | `{'a':None, 'b':None}` |
| `get(k[,d])`    | Returns value for key or default         | `{'a':1}.get('a')`          | `1`                |
| `items()`       | Returns view of (key, value) pairs       | `{'a':1}.items()`           | `dict_items([('a', 1)])` |
| `keys()`        | Returns view of keys                     | `{'a':1}.keys()`            | `dict_keys(['a'])` |
| `pop(k[,d])`    | Removes key and returns its value        | `{'a':1}.pop('a')`          | `1`                |
| `popitem()`     | Removes and returns last inserted item   | `{'a':1,'b':2}.popitem()`   | `('b', 2)`         |
| `setdefault(k[,d])`| Returns value if exists, else inserts with default | `{}.setdefault('a',1)` | `1` (dict becomes `{'a':1}`) |
| `update(other)` | Updates dict with key/value pairs        | `{'a':1}.update({'b':2})`   | `{'a':1, 'b':2}`   |
| `values()`      | Returns view of values                   | `{'a':1}.values()`          | `dict_values([1])` |
___
___

# `Set Methods`

| Method                      | Shortcut | Description | Example | Result |
|-----------------------------|----------|-------------|---------|--------|
| `add(element)`              |          | Adds an element to the set | `s = {1,2}; s.add(3)` | `{1, 2, 3}` |
| `clear()`                   |          | Removes all elements from the set | `s = {1,2}; s.clear()` | `set()` |
| `copy()`                    |          | Returns a shallow copy of the set | `s = {1,2}; s.copy()` | `{1, 2}` |
| `difference(other_set)`     | `-`      | Returns new set with elements in this set but not in others | `{1,2}.difference({2,3})` | `{1}` |
| `difference_update(other_set)` | `-=`  | Updates set by removing elements found in others | `s = {1,2}; s.difference_update({2})` | `{1}` |
| `discard(element)`          |          | Removes specified element if present | `s = {1,2}; s.discard(1)` | `{2}` |
| `intersection(other_set)`   | `&`      | Returns new set with elements common to all sets | `{1,2} & {2,3}` | `{2}` |
| `intersection_update(other_set)` | `&=` | Updates set keeping only elements found in all sets | `s = {1,2}; s &= {2,3}` | `{2}` |
| `isdisjoint(other_set)`     |          | Returns True if sets have no common elements | `{1}.isdisjoint({2})` | `True` |
| `issubset(other_set)`       | `<=`     | Returns True if all elements of set are in other set | `{1}.issubset({1,2})` | `True` |
|                             | `<`      | Returns True if proper subset (subset but not equal) | `{1} < {1,2}` | `True` |
| `issuperset(other_set)`     | `>=`     | Returns True if set contains all elements of other set | `{1,2} >= {1}` | `True` |
|                             | `>`      | Returns True if proper superset (superset but not equal) | `{1,2} > {1}` | `True` |
| `pop()`                     |          | Removes and returns arbitrary element | `s = {1}; s.pop()` | `1` (set becomes `set()`) |
| `remove(element)`           |          | Removes specified element | `s = {1,2}; s.remove(1)` | `{2}` |
| `symmetric_difference(other_set)` | `^` | Returns new set with elements in either set but not both | `{1,2} ^ {2,3}` | `{1, 3}` |
| `symmetric_difference_update(other_set)` | `^=` | Updates set keeping only elements in either set but not both | `s = {1,2}; s ^= {2,3}` | `{1, 3}` |
| `union(other_set)`          | `\|`     | Returns new set containing all elements from all sets | `{1} \| {2}` | `{1, 2}` |
| `update(other_set)`         | `\|=`    | Updates set by adding elements from others | `s = {1}; s.update({2})` | `{1, 2}` |

___
___

# `Tuple Methods`

| Method       | Description | Example | Result |
|--------------|-------------|---------|--------|
| `count(value)` | Returns the number of occurrences of a value in the tuple | `(1, 2, 2, 3).count(2)` | `2` |
| `index(value)` | Returns the first index where the value is found | `('a', 'b', 'c').index('b')` | `1` |
# `Python Methods `
# `String Methods`

| Method               | Description                                                                 | Example                          | Result                     |
|----------------------|-----------------------------------------------------------------------------|----------------------------------|----------------------------|
| `capitalize()`       | Converts the first character to uppercase                                   | `"hello".capitalize()`          | `"Hello"`                  |
| `casefold()`         | Converts string to lowercase (stronger than `lower()`)                     | `"HELLO".casefold()`            | `"hello"`                  |
| `center(width)`      | Returns a centered string                                                  | `"hi".center(5)`                | `" hi  "`                  |
| `count(sub)`         | Returns occurrences of substring                                           | `"hello".count('l')`            | `2`                        |
| `encode()`           | Returns encoded version of string                                          | `"hi".encode('utf-8')`          | `b'hi'`                    |
| `endswith(suffix)`   | Checks if string ends with suffix                                          | `"hello".endswith('lo')`        | `True`                     |
| `expandtabs()`       | Sets tab size                                                              | `"a\tb".expandtabs(4)`          | `"a   b"`                  |
| `find(sub)`          | Returns index of first substring occurrence                                | `"hello".find('e')`             | `1`                        |
| `format()`           | Formats string with values                                                 | `"{}".format('hi')`             | `"hi"`                     |
| `format_map()`       | Formats using dictionary                                                   | `"{x}".format_map({'x':1})`     | `"1"`                      |
| `index(sub)`         | Like find() but raises ValueError if not found                             | `"hello".index('e')`            | `1`                        |
| `isalnum()`          | Checks alphanumeric characters                                             | `"abc123".isalnum()`            | `True`                     |
| `isalpha()`          | Checks alphabetic characters                                               | `"abc".isalpha()`               | `True`                     |
| `isascii()`          | Checks ASCII characters                                                    | `"abc".isascii()`               | `True`                     |
| `isdecimal()`        | Checks decimal characters                                                  | `"123".isdecimal()`             | `True`                     |
| `isdigit()`          | Checks digit characters                                                    | `"123".isdigit()`               | `True`                     |
| `isidentifier()`     | Checks valid identifier                                                    | `"var_name".isidentifier()`     | `True`                     |
| `islower()`          | Checks lowercase characters                                                | `"hello".islower()`             | `True`                     |
| `isnumeric()`        | Checks numeric characters                                                  | `"١٢٣".isnumeric()`             | `True`                     |
| `isprintable()`      | Checks printable characters                                                | `"hello".isprintable()`         | `True`                     |
| `isspace()`          | Checks whitespace characters                                               | `"   ".isspace()`               | `True`                     |
| `istitle()`          | Checks titlecase string                                                    | `"Hello World".istitle()`       | `True`                     |
| `isupper()`          | Checks uppercase characters                                                | `"HELLO".isupper()`             | `True`                     |
| `join(iterable)`     | Joins iterable elements                                                    | `",".join(['a','b'])`           | `"a,b"`                    |
| `ljust(width)`       | Returns left-justified string                                              | `"hi".ljust(5)`                 | `"hi   "`                  |
| `lower()`            | Converts to lowercase                                                      | `"HELLO".lower()`               | `"hello"`                  |
| `lstrip()`           | Removes leading whitespace                                                 | `"  hi  ".lstrip()`             | `"hi  "`                   |
| `maketrans()`        | Creates translation table                                                  | `str.maketrans('a','b')`        | `{97: 98}`                 |
| `partition(sep)`     | Splits at first separator                                                 | `"hello".partition('l')`        | `('he', 'l', 'lo')`        |
| `replace(old,new)`   | Replaces substring                                                        | `"hi".replace('i','ello')`      | `"hello"`                  |
| `rfind(sub)`         | Searches from end                                                         | `"hello".rfind('l')`            | `3`                        |
| `rindex(sub)`        | Like rfind() but raises error if not found                                | `"hello".rindex('l')`           | `3`                        |
| `rjust(width)`       | Returns right-justified string                                            | `"hi".rjust(5)`                 | `"   hi"`                  |
| `rpartition(sep)`    | Splits at last separator                                                 | `"hello".rpartition('l')`       | `('hel', 'l', 'o')`        |
| `rsplit()`           | Splits from end                                                          | `"a b c".rsplit()`              | `['a', 'b', 'c']`          |
| `rstrip()`           | Removes trailing whitespace                                               | `"  hi  ".rstrip()`             | `"  hi"`                   |
| `split()`            | Splits string                                                            | `"a b c".split()`               | `['a', 'b', 'c']`          |
| `splitlines()`       | Splits at line breaks                                                    | `"a\nb".splitlines()`           | `['a', 'b']`               |
| `startswith(prefix)` | Checks starting prefix                                                   | `"hello".startswith('he')`      | `True`                     |
| `strip()`            | Removes both leading and trailing whitespace                              | `"  hi  ".strip()`              | `"hi"`                     |
| `swapcase()`         | Swaps cases                                                              | `"Hello".swapcase()`            | `"hELLO"`                  |
| `title()`            | Converts to titlecase                                                    | `"hello world".title()`         | `"Hello World"`            |
| `translate()`        | Translates characters                                                    | `"abc".translate({97:98})`      | `"bbc"`                    |
| `upper()`            | Converts to uppercase                                                    | `"hello".upper()`               | `"HELLO"`                  |
| `zfill(width)`       | Fills with zeros on left                                                 | `"42".zfill(5)`                 | `"00042"`                  |

# `File Methods`

| Method           | Description                                                                 | Example                          | Result                     |
|------------------|-----------------------------------------------------------------------------|----------------------------------|----------------------------|
| `close()`        | Closes the file                                                             | `f = open('file.txt'); f.close()`| -                          |
| `detach()`       | Separates raw stream from buffer                                            | `f.detach()`                     | -                          |
| `fileno()`       | Returns file descriptor                                                     | `f.fileno()`                     | `3`                        |
| `flush()`        | Flushes internal buffer                                                     | `f.flush()`                      | -                          |
| `isatty()`       | Checks if stream is interactive                                             | `f.isatty()`                     | `False`                    |
| `read()`         | Reads file content                                                          | `f.read()`                       | File content               |
| `readable()`     | Checks if file is readable                                                  | `f.readable()`                   | `True`                     |
| `readline()`     | Reads single line                                                           | `f.readline()`                   | First line                 |
| `readlines()`    | Reads all lines                                                             | `f.readlines()`                  | List of lines              |
| `seek(offset)`   | Changes file position                                                       | `f.seek(0)`                      | -                          |
| `seekable()`     | Checks if file supports random access                                       | `f.seekable()`                   | `True`                     |
| `tell()`         | Returns current position                                                    | `f.tell()`                       | `0`                        |
| `truncate()`     | Resizes file                                                                | `f.truncate(10)`                 | -                          |
| `writable()`     | Checks if file is writable                                                  | `f.writable()`                   | `True`                     |
| `write()`        | Writes string to file                                                       | `f.write('hi')`                  | Characters written         |
| `writelines()`   | Writes list of strings                                                      | `f.writelines(['a','b'])`        | -                          |
# `Python Methods`
## `String Methods`

| #  | Method               | الوصف                                                                 | Example                          | Result                     |
|----|----------------------|---------------------------------------------------------------------|----------------------------------|----------------------------|
| 1  | `capitalize()`       | تحويل الحرف الأول إلى حرف كبير                                       | `"hello".capitalize()`          | `"Hello"`                  |
| 2  | `casefold()`         | تحويل السلسلة إلى أحرف صغيرة                                         | `"HELLO".casefold()`            | `"hello"`                  |
| 3  | `center(width)`      | إرجاع سلسلة مركزة                                                    | `"hi".center(5)`                | `" hi  "`                  |
| 4  | `count(sub)`         | حساب عدد التكرارات                                                   | `"hello".count('l')`            | `2`                        |
| 5  | `encode()`           | ترميز السلسلة                                                        | `"سلام".encode('utf-8')`        | `b'\xd8\xb3\xd9\x84\xd8\xa7\xd9\x85'` |
| 6  | `endswith(suffix)`   | التحقق من انتهاء السلسلة                                             | `"hello".endswith('lo')`        | `True`                     |
| 7  | `expandtabs()`       | توسيع علامات التبويب                                                 | `"a\tb".expandtabs(4)`          | `"a   b"`                  |
| 8  | `find(sub)`          | البحث عن نص وإرجاع موقعه                                             | `"hello".find('e')`             | `1`                        |
| 9  | `format()`           | تنسيق السلسلة                                                       | `"{}".format('hi')`             | `"hi"`                     |
| 10 | `format_map()`       | تنسيق السلسلة باستخدام قاموس                                         | `"{x}".format_map({'x':1})`     | `"1"`                      |
| 11 | `index(sub)`         | البحث عن نص وإرجاع موقعه (يرفع خطأ إذا لم يوجد)                      | `"hello".index('e')`            | `1`                        |
| 12 | `isalnum()`          | التحقق إذا كانت جميع الأحرف أبجدية رقمية                              | `"abc123".isalnum()`            | `True`                     |
| 13 | `isalpha()`          | التحقق إذا كانت جميع الأحرف أبجدية                                    | `"abc".isalpha()`               | `True`                     |
| 14 | `isascii()`          | التحقق إذا كانت جميع الأحرف أسكي                                      | `"abc".isascii()`               | `True`                     |
| 15 | `isdecimal()`        | التحقق إذا كانت جميع الأحرف أرقام عشرية                               | `"123".isdecimal()`             | `True`                     |
| 16 | `isdigit()`          | التحقق إذا كانت جميع الأحرف أرقام                                     | `"123".isdigit()`               | `True`                     |
| 17 | `isidentifier()`     | التحقق إذا كانت السلسلة معرف صالح                                     | `"var_name".isidentifier()`     | `True`                     |
| 18 | `islower()`          | التحقق إذا كانت جميع الأحرف صغيرة                                     | `"hello".islower()`             | `True`                     |
| 19 | `isnumeric()`        | التحقق إذا كانت جميع الأحرف رقمية                                     | `"١٢٣".isnumeric()`             | `True`                     |
| 20 | `isprintable()`      | التحقق إذا كانت جميع الأحرف قابلة للطباعة                             | `"hello".isprintable()`         | `True`                     |
| 21 | `isspace()`          | التحقق إذا كانت جميع الأحرف مسافات                                    | `"   ".isspace()`               | `True`                     |
| 22 | `istitle()`          | التحقق إذا كانت السلسلة بعنوان                                        | `"Hello World".istitle()`       | `True`                     |
| 23 | `isupper()`          | التحقق إذا كانت جميع الأحرف كبيرة                                     | `"HELLO".isupper()`             | `True`                     |
| 24 | `join(iterable)`     | ربط العناصر بسلسلة                                                   | `",".join(['a','b'])`           | `"a,b"`                    |
| 25 | `ljust(width)`       | محاذاة السلسلة لليسار                                                | `"hi".ljust(5)`                 | `"hi   "`                  |
| 26 | `lower()`            | تحويل السلسلة إلى أحرف صغيرة                                         | `"HELLO".lower()`               | `"hello"`                  |
| 27 | `lstrip()`           | إزالة المسافات من الجهة اليسرى                                       | `"  hi  ".lstrip()`             | `"hi  "`                   |
| 28 | `maketrans()`        | إنشاء جدول ترجمة                                                     | `str.maketrans('a','b')`        | `{97: 98}`                 |
| 29 | `partition(sep)`     | تقسيم السلسلة إلى 3 أجزاء                                            | `"hello".partition('l')`        | `('he', 'l', 'lo')`        |
| 30 | `replace(old,new)`   | استبدال نص بآخر                                                      | `"hi".replace('i','ello')`      | `"hello"`                  |
| 31 | `rfind(sub)`         | البحث عن نص من النهاية                                               | `"hello".rfind('l')`            | `3`                        |
| 32 | `rindex(sub)`        | البحث عن نص من النهاية (يرفع خطأ إذا لم يوجد)                         | `"hello".rindex('l')`           | `3`                        |
| 33 | `rjust(width)`       | محاذاة السلسلة لليمين                                                | `"hi".rjust(5)`                 | `"   hi"`                  |
| 34 | `rpartition(sep)`    | تقسيم السلسلة إلى 3 أجزاء من النهاية                                 | `"hello".rpartition('l')`       | `('hel', 'l', 'o')`        |
| 35 | `rsplit()`           | تقسيم السلسلة من النهاية                                             | `"a b c".rsplit()`              | `['a', 'b', 'c']`          |
| 36 | `rstrip()`           | إزالة المسافات من الجهة اليمنى                                       | `"  hi  ".rstrip()`             | `"  hi"`                   |
| 37 | `split()`            | تقسيم السلسلة                                                        | `"a b c".split()`               | `['a', 'b', 'c']`          |
| 38 | `splitlines()`       | تقسيم السلسلة عند نهايات الأسطر                                       | `"a\nb".splitlines()`           | `['a', 'b']`               |
| 39 | `startswith(prefix)` | التحقق من بداية السلسلة                                              | `"hello".startswith('he')`      | `True`                     |
| 40 | `strip()`            | إزالة المسافات من الجانبين                                           | `"  hi  ".strip()`              | `"hi"`                     |
| 41 | `swapcase()`         | عكس حالة الأحرف                                                      | `"Hello".swapcase()`            | `"hELLO"`                  |
| 42 | `title()`            | تحويل أول حرف من كل كلمة إلى كبير                                     | `"hello world".title()`         | `"Hello World"`            |
| 43 | `translate()`        | ترجمة السلسلة                                                       | `"abc".translate({97:98})`      | `"bbc"`                    |
| 44 | `upper()`            | تحويل السلسلة إلى أحرف كبيرة                                         | `"hello".upper()`               | `"HELLO"`                  |
| 45 | `zfill(width)`       | إضافة أصفار من الجهة اليسرى                                          | `"42".zfill(5)`                 | `"00042"`                  |
<br><br><br>
## `File Methods`

| #  | Method           | الوصف                                                                 | Example                          | Result                     |
|----|------------------|---------------------------------------------------------------------|----------------------------------|----------------------------|
| 1  | `close()`        | إغلاق الملف                                                          | `f = open('file.txt'); f.close()`| -                          |
| 2  | `detach()`       | فصل الدفق الخام من المخزن المؤقت                                     | `f.detach()`                     | -                          |
| 3  | `fileno()`       | إرجاع رقم الدفق                                                      | `f.fileno()`                     | `3`                        |
| 4  | `flush()`        | تفريغ المخزن المؤقت                                                  | `f.flush()`                      | -                          |
| 5  | `isatty()`       | التحقق إذا كان الدفق تفاعلي                                          | `f.isatty()`                     | `False`                    |
| 6  | `read()`         | قراءة محتوى الملف                                                    | `f.read()`                       | محتوى الملف                 |
| 7  | `readable()`     | التحقق إذا كان الملف قابل للقراءة                                     | `f.readable()`                   | `True`                     |
| 8  | `readline()`     | قراءة سطر واحد                                                       | `f.readline()`                   | السطر الأول                |
| 9  | `readlines()`    | قراءة جميع الأسطر                                                    | `f.readlines()`                  | قائمة بالأسطر              |
| 10 | `seek(offset)`   | تغيير موضع الملف                                                     | `f.seek(0)`                      | -                          |
| 11 | `seekable()`     | التحقق إذا كان يمكن تغيير موضع الملف                                  | `f.seekable()`                   | `True`                     |
| 12 | `tell()`         | إرجاع موضع الملف الحالي                                              | `f.tell()`                       | `0`                        |
| 13 | `truncate()`     | تقليص حجم الملف                                                      | `f.truncate(10)`                 | -                          |
| 14 | `writable()`     | التحقق إذا كان الملف قابل للكتابة                                     | `f.writable()`                   | `True`                     |
| 15 | `write()`        | كتابة نص إلى الملف                                                   | `f.write('hi')`                  | عدد الأحرف المكتوبة        |
| 16 | `writelines()`   | كتابة قائمة نصوص إلى الملف                                           | `f.writelines(['a','b'])`        | -                          |

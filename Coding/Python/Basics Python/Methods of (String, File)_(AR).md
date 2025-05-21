# `Python Methods `
## `String Methods`

| Method               | الوصف                                                                 | Example                          | Result                     |
|----------------------|---------------------------------------------------------------------|----------------------------------|----------------------------|
| `capitalize()`       | تحويل الحرف الأول إلى حرف كبير                                       | `"hello".capitalize()`          | `"Hello"`                  |
| `casefold()`         | تحويل السلسلة إلى أحرف صغيرة                                         | `"HELLO".casefold()`            | `"hello"`                  |
| `center(width)`      | إرجاع سلسلة مركزة                                                    | `"hi".center(5)`                | `" hi  "`                  |
| `count(sub)`         | حساب عدد التكرارات                                                   | `"hello".count('l')`            | `2`                        |
| `encode()`           | ترميز السلسلة                                                        | `"سلام".encode('utf-8')`        | `b'\xd8\xb3\xd9\x84\xd8\xa7\xd9\x85'` |
| `endswith(suffix)`   | التحقق من انتهاء السلسلة                                             | `"hello".endswith('lo')`        | `True`                     |
| `expandtabs()`       | توسيع علامات التبويب                                                 | `"a\tb".expandtabs(4)`          | `"a   b"`                  |
| `find(sub)`          | البحث عن نص وإرجاع موقعه                                             | `"hello".find('e')`             | `1`                        |
| `format()`           | تنسيق السلسلة                                                       | `"{}".format('hi')`             | `"hi"`                     |
| `format_map()`       | تنسيق السلسلة باستخدام قاموس                                         | `"{x}".format_map({'x':1})`     | `"1"`                      |
| `index(sub)`         | البحث عن نص وإرجاع موقعه (يرفع خطأ إذا لم يوجد)                      | `"hello".index('e')`            | `1`                        |
| `isalnum()`          | التحقق إذا كانت جميع الأحرف أبجدية رقمية                              | `"abc123".isalnum()`            | `True`                     |
| `isalpha()`          | التحقق إذا كانت جميع الأحرف أبجدية                                    | `"abc".isalpha()`               | `True`                     |
| `isascii()`          | التحقق إذا كانت جميع الأحرف أسكي                                      | `"abc".isascii()`               | `True`                     |
| `isdecimal()`        | التحقق إذا كانت جميع الأحرف أرقام عشرية                               | `"123".isdecimal()`             | `True`                     |
| `isdigit()`          | التحقق إذا كانت جميع الأحرف أرقام                                     | `"123".isdigit()`               | `True`                     |
| `isidentifier()`     | التحقق إذا كانت السلسلة معرف صالح                                     | `"var_name".isidentifier()`     | `True`                     |
| `islower()`          | التحقق إذا كانت جميع الأحرف صغيرة                                     | `"hello".islower()`             | `True`                     |
| `isnumeric()`        | التحقق إذا كانت جميع الأحرف رقمية                                     | `"١٢٣".isnumeric()`             | `True`                     |
| `isprintable()`      | التحقق إذا كانت جميع الأحرف قابلة للطباعة                             | `"hello".isprintable()`         | `True`                     |
| `isspace()`          | التحقق إذا كانت جميع الأحرف مسافات                                    | `"   ".isspace()`               | `True`                     |
| `istitle()`          | التحقق إذا كانت السلسلة بعنوان                                        | `"Hello World".istitle()`       | `True`                     |
| `isupper()`          | التحقق إذا كانت جميع الأحرف كبيرة                                     | `"HELLO".isupper()`             | `True`                     |
| `join(iterable)`     | ربط العناصر بسلسلة                                                   | `",".join(['a','b'])`           | `"a,b"`                    |
| `ljust(width)`       | محاذاة السلسلة لليسار                                                | `"hi".ljust(5)`                 | `"hi   "`                  |
| `lower()`            | تحويل السلسلة إلى أحرف صغيرة                                         | `"HELLO".lower()`               | `"hello"`                  |
| `lstrip()`           | إزالة المسافات من الجهة اليسرى                                       | `"  hi  ".lstrip()`             | `"hi  "`                   |
| `maketrans()`        | إنشاء جدول ترجمة                                                     | `str.maketrans('a','b')`        | `{97: 98}`                 |
| `partition(sep)`     | تقسيم السلسلة إلى 3 أجزاء                                            | `"hello".partition('l')`        | `('he', 'l', 'lo')`        |
| `replace(old,new)`   | استبدال نص بآخر                                                      | `"hi".replace('i','ello')`      | `"hello"`                  |
| `rfind(sub)`         | البحث عن نص من النهاية                                               | `"hello".rfind('l')`            | `3`                        |
| `rindex(sub)`        | البحث عن نص من النهاية (يرفع خطأ إذا لم يوجد)                         | `"hello".rindex('l')`           | `3`                        |
| `rjust(width)`       | محاذاة السلسلة لليمين                                                | `"hi".rjust(5)`                 | `"   hi"`                  |
| `rpartition(sep)`    | تقسيم السلسلة إلى 3 أجزاء من النهاية                                 | `"hello".rpartition('l')`       | `('hel', 'l', 'o')`        |
| `rsplit()`           | تقسيم السلسلة من النهاية                                             | `"a b c".rsplit()`              | `['a', 'b', 'c']`          |
| `rstrip()`           | إزالة المسافات من الجهة اليمنى                                       | `"  hi  ".rstrip()`             | `"  hi"`                   |
| `split()`            | تقسيم السلسلة                                                        | `"a b c".split()`               | `['a', 'b', 'c']`          |
| `splitlines()`       | تقسيم السلسلة عند نهايات الأسطر                                       | `"a\nb".splitlines()`           | `['a', 'b']`               |
| `startswith(prefix)` | التحقق من بداية السلسلة                                              | `"hello".startswith('he')`      | `True`                     |
| `strip()`            | إزالة المسافات من الجانبين                                           | `"  hi  ".strip()`              | `"hi"`                     |
| `swapcase()`         | عكس حالة الأحرف                                                      | `"Hello".swapcase()`            | `"hELLO"`                  |
| `title()`            | تحويل أول حرف من كل كلمة إلى كبير                                     | `"hello world".title()`         | `"Hello World"`            |
| `translate()`        | ترجمة السلسلة                                                       | `"abc".translate({97:98})`      | `"bbc"`                    |
| `upper()`            | تحويل السلسلة إلى أحرف كبيرة                                         | `"hello".upper()`               | `"HELLO"`                  |
| `zfill(width)`       | إضافة أصفار من الجهة اليسرى                                          | `"42".zfill(5)`                 | `"00042"`                  |

## `File Methods`

| Method           | الوصف                                                                 | Example                          | Result                     |
|------------------|---------------------------------------------------------------------|----------------------------------|----------------------------|
| `close()`        | إغلاق الملف                                                          | `f = open('file.txt'); f.close()`| -                          |
| `detach()`       | فصل الدفق الخام من المخزن المؤقت                                     | `f.detach()`                     | -                          |
| `fileno()`       | إرجاع رقم الدفق                                                      | `f.fileno()`                     | `3`                        |
| `flush()`        | تفريغ المخزن المؤقت                                                  | `f.flush()`                      | -                          |
| `isatty()`       | التحقق إذا كان الدفق تفاعلي                                          | `f.isatty()`                     | `False`                    |
| `read()`         | قراءة محتوى الملف                                                    | `f.read()`                       | محتوى الملف                 |
| `readable()`     | التحقق إذا كان الملف قابل للقراءة                                     | `f.readable()`                   | `True`                     |
| `readline()`     | قراءة سطر واحد                                                       | `f.readline()`                   | السطر الأول                |
| `readlines()`    | قراءة جميع الأسطر                                                    | `f.readlines()`                  | قائمة بالأسطر              |
| `seek(offset)`   | تغيير موضع الملف                                                     | `f.seek(0)`                      | -                          |
| `seekable()`     | التحقق إذا كان يمكن تغيير موضع الملف                                  | `f.seekable()`                   | `True`                     |
| `tell()`         | إرجاع موضع الملف الحالي                                              | `f.tell()`                       | `0`                        |
| `truncate()`     | تقليص حجم الملف                                                      | `f.truncate(10)`                 | -                          |
| `writable()`     | التحقق إذا كان الملف قابل للكتابة                                     | `f.writable()`                   | `True`                     |
| `write()`        | كتابة نص إلى الملف                                                   | `f.write('hi')`                  | عدد الأحرف المكتوبة        |
| `writelines()`   | كتابة قائمة نصوص إلى الملف                                           | `f.writelines(['a','b'])`        | -                          |

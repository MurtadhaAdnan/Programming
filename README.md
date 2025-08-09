<div dir="rtl">
  
# SVM باختصار

## الفكرة الأساسية
إيجاد **مستوى فصل** خطي:

$$
\langle \boldsymbol{w}, \boldsymbol{x} \rangle + b = 0
$$

## معادلة التحسين
لتعظيم الهامش:

$$
\min_{\boldsymbol{w},b} \frac{1}{2}\|\boldsymbol{w}\|^2
$$

بشرط:

$$
y_i(\langle \boldsymbol{w}, \boldsymbol{x}_i \rangle + b) \geq 1
$$

## الصيغة المزدوجة
حل بدلالة مضاعفات لاغرانج:

$$
\max_{\alpha} \sum \alpha_i - \frac{1}{2}\sum \alpha_i \alpha_j y_i y_j \langle \boldsymbol{x}_i, \boldsymbol{x}_j \rangle
$$

</div>



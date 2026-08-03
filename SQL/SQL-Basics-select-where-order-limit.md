# استعلام البيانات: SELECT / WHERE / ORDER BY / LIMIT / AS

## الكود
```sql
-- ترتيب تصاعدي (من A لـ Z)
SELECT student.name, student.major
FROM student
ORDER BY name ASC;

-- ترتيب تنازلي (من Z لـ A)
SELECT student.name, student.major
FROM student
ORDER BY name DESC;

-- ترتيب بأكتر من عمود
SELECT student.name, student.major
FROM student
ORDER BY major, student_id DESC;

-- جلب أول عدد صفوف بس (مفيدة جدًا في قواعد البيانات الكبيرة)
SELECT * FROM student LIMIT 2;

-- شرط IN: القيمة تبقى واحدة من مجموعة
SELECT name, major
FROM student
WHERE name IN ('Jack', 'Kate');

-- شرط NOT LIKE: استبعاد قيم معينة
SELECT * FROM products WHERE name NOT LIKE 'TV%';

-- AS: تغيير اسم العمود وقت العرض بس (مش بيغير اسمه في الجدول)
SELECT id AS product_id, is_sale AS on_sale FROM products;

-- دمج WHERE و ORDER BY مع بعض
SELECT * FROM products WHERE price > 20 ORDER BY created_at ASC;

-- دمج WHERE و LIMIT مع بعض
SELECT * FROM products WHERE price > 20 LIMIT 10;
```

## ملاحظات
- `AS` بتستخدم لإعادة تسمية العمود في نتيجة العرض فقط، مش بتغير اسم العمود الأصلي في الجدول.
- `LIMIT` بترجع أول عدد صفوف حسب الرقم اللي بتحطه، مفيدة جدًا لما تيجي تختبر كويري على جدول ضخم.
- `ORDER BY` من غير `ASC`/`DESC` بيبقى تصاعدي (ASC) بشكل افتراضي.

## مرتبط
- [[SQL-Basics-dml-insert-update-delete]]
- [[SQL-Wildcards-like]]

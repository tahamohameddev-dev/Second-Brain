# DML - إضافة وتعديل وحذف البيانات (INSERT / UPDATE / DELETE)

## الكود
```sql
-- إضافة صف بأعمدة محددة (الباقي بياخد القيمة الافتراضية أو NULL)
INSERT INTO student(student_id, name) VALUES(2, 'Kate');

-- إضافة صف بكل القيم بالترتيب
INSERT INTO student VALUES(4, 'Jack', 'Biology');

-- تعديل بيانات موجودة بناءً على شرط
UPDATE student
SET major = 'Bio'
WHERE major = 'Biology';

-- حذف صف بناءً على شرط
DELETE FROM student
WHERE student_id = 5;
```

## ملاحظات
- لو مكتبتش الأعمدة في الـ INSERT، لازم تكتب القيم بنفس ترتيب الأعمدة في الجدول بالظبط.
- لازم يكون فيه `WHERE` في الـ `UPDATE` و`DELETE`، لو نسيته هيتعدل أو يتمسح كل الجدول بالكامل!
- ممكن أكتر من صف يتحدثوا بنفس أمر الـ `UPDATE` لو الشرط بتاعهم بيتحقق في أكتر من صف.

## أخطاء شائعة
- نسيان `WHERE` في `UPDATE`/`DELETE` بيأثر على الجدول كله مش صف واحد بس.
- الـ VARCHAR له حد أقصى للطول (زي `VARCHAR(20)`)، لو القيمة أطول هتترفض أو تتقطع حسب إعدادات القاعدة.

## مرتبط
- [[SQL-Basics-ddl-create-alter-drop]]
- [[SQL-Basics-select-where-order-limit]]

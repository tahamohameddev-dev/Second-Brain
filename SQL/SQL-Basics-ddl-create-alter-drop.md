# DDL - إنشاء وتعديل وحذف الجداول (CREATE / ALTER / DROP)

## الكود
```sql
-- إنشاء جدول
CREATE TABLE student (
    student_id INT PRIMARY KEY,
    name VARCHAR(20),
    major VARCHAR(20)
);

-- عرض تفاصيل الجدول (الأعمدة وأنواعها)
DESCRIBE student;

-- حذف الجدول بالكامل
DROP TABLE student;

-- إضافة عمود جديد لجدول موجود
ALTER TABLE student ADD gpa DECIMAL(3, 2);

-- حذف عمود من جدول
ALTER TABLE student DROP COLUMN gpa;

-- عمود بقيمة افتراضية لو محدش حط قيمة
CREATE TABLE student (
    student_id INT PRIMARY KEY,
    name VARCHAR(20),
    major VARCHAR(20) DEFAULT 'undecided'
);

-- توليد ID تلقائي (بيزود نفسه لوحده) - نسخة MySQL
CREATE TABLE student (
    student_id INT AUTO_INCREMENT,
    name VARCHAR(20),
    major VARCHAR(20) DEFAULT 'undecided',
    PRIMARY KEY(student_id)
);

-- توليد ID عشوائي تلقائي - نسخة PostgreSQL
-- id SERIAL PRIMARY KEY

-- توليد وقت الإنشاء تلقائيًا - نسخة PostgreSQL
-- created_at TIMESTAMP DEFAULT NOW()
```

## ملاحظات
- `AUTO_INCREMENT` بتستخدم في MySQL، أما `SERIAL` فهي بديلها في PostgreSQL.
- `DEFAULT` بتحط قيمة تلقائية للعمود لو المستخدم مبعتش قيمة له وقت الـ INSERT.
- `DROP TABLE` بيمسح الجدول نهائيًا بكل بياناته، لازم تتأكد قبل ما تنفذه.
- `DESCRIBE` بتوريك بنية الجدول (أسماء الأعمدة، النوع، هل ممكن يبقى NULL...).

## مرتبط
- [[SQL-Basics-dml-insert-update-delete]]
- [[SQL-Postgres-serial-timestamp]]

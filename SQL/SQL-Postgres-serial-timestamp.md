# توليد ID و Timestamp تلقائي في PostgreSQL

## الكود
```sql
-- توليد ID تلقائي متسلسل (بديل AUTO_INCREMENT بتاع MySQL)
CREATE TABLE posts (
    id SERIAL PRIMARY KEY,
    title VARCHAR NOT NULL
);

-- توليد وقت الإنشاء تلقائيًا لحظة إضافة الصف
CREATE TABLE posts (
    id SERIAL PRIMARY KEY,
    title VARCHAR NOT NULL,
    created_at TIMESTAMP DEFAULT NOW()
);
```

## ملاحظات
- `SERIAL` هي الطريقة الشائعة في PostgreSQL لعمل ID بيزود نفسه تلقائيًا (زي `AUTO_INCREMENT` في MySQL بالظبط في الوظيفة).
- `TIMESTAMP DEFAULT NOW()` بتسجل تاريخ ووقت إضافة الصف تلقائيًا من غير ما تكتبها إنت وقت الـ INSERT.

## مرتبط
- [[SQL-Basics-ddl-create-alter-drop]]
- [[SQL-Postgres-psql-commands]]

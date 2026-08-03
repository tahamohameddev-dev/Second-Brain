# أوامر psql (سطر أوامر PostgreSQL)

## الكود
```sql
-- عرض كل قواعد البيانات
\l

-- إنشاء قاعدة بيانات جديدة
CREATE DATABASE test_db;

-- الدخول جوه القاعدة اللي عملتها
\c test_db

-- عرض كل الجداول في القاعدة الحالية
\dt

-- عرض تفاصيل جدول معين
\d posts

-- معرفة انت داخل أنهي قاعدة دلوقتي
\conninfo

-- مسح جدول معين
DROP TABLE users;

-- مسح قاعدة بيانات بالكامل (لازم تخرج منها الأول لقاعدة تانية زي postgres)
\c postgres
DROP DATABASE test_db;

-- الخروج من psql
\q
```

## ملاحظات
- الأوامر اللي بتبدأ بـ `\` (backslash) دي أوامر خاصة بـ `psql` نفسه، مش SQL عادي — بتشتغل بس جوه الـ terminal بتاع psql.
- لازم تخرج من أي قاعدة بيانات (`\c` لقاعدة تانية زي `postgres`) قبل ما تقدر تمسحها بـ `DROP DATABASE`.
- من الـ CMD مباشرة (قبل الدخول لـ MySQL بديل): `mysql -u root -p`

## مرتبط
- [[SQL-Basics-ddl-create-alter-drop]]
- [[SQL-Postgres-serial-timestamp]]

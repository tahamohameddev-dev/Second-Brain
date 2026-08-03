# Git - الفروع (Branches)

## الكود
```bash
# تشوف انت في أنهي فرع دلوقتي
git branch

# تنشئ فرع جديد
git branch feature-api

# تتنقل لفرع تاني
git checkout feature-api

# تنشئ وتتنقل في أمر واحد
git checkout -b feature-api

# ترجع للـ main
git checkout main

# تدمج الفرع في main (وانت واقف في main)
git merge feature-api

# تمسح فرع بعد ما تخلص منه
git branch -d feature-api
```

## ملاحظات
- الفروع بتخليك تشتغل على ميزة جديدة أو تجربة من غير ما تأثر على الكود الرئيسي (main) لحد ما تتأكد إنها شغالة.
- لازم تكون واقف في `main` وقت عمل `git merge` عشان يدمج الفرع التاني فيه صح.
- `git branch -d` بترفض تمسح فرع لسه فيه تعديلات مادمجتهاش، استخدم `-D` (كبيتال) لو متأكد عايز تمسحه بالقوة.

## تمرين سريع
1. `git init` في مجلد المشروع
2. اعمل فرع اسمه `feature-database-setup`
3. جرب `CREATE DATABASE` و `DROP DATABASE` على قاعدة تجريبية بينك وبين نفسك

## مرتبط
- [[Git-Basics-init-commit-remote]]

# الربط بين الجداول (JOIN / LEFT JOIN / RIGHT JOIN)

## الكود
```sql
-- INNER JOIN: هات بس الصفوف اللي فيها تطابق في الجدولين
SELECT employee.emp_id, employee.first_name, branch.branch_name
FROM employee
JOIN branch
ON employee.emp_id = branch.mgr_id;

-- LEFT JOIN: هات كل صفوف الجدول اللي على الشمال (employee) حتى لو مفيش تطابق
SELECT employee.emp_id, employee.first_name, branch.branch_name
FROM employee
LEFT JOIN branch
ON employee.emp_id = branch.mgr_id;

-- RIGHT JOIN: هات كل صفوف الجدول اللي على اليمين (branch) حتى لو مفيش تطابق
SELECT employee.emp_id, employee.first_name, branch.branch_name
FROM employee
RIGHT JOIN branch
ON employee.emp_id = branch.mgr_id;
```

## ملاحظات
- **JOIN (Inner Join)**: بيرجع بس الصفوف اللي ليها تطابق في الجدولين. لو موظف مالوش فرع بيديره، مش هيظهر.
- **LEFT JOIN**: بيرجع كل صفوف الجدول الأول (اللي فاتح بيه FROM) + التطابقات من التاني، ولو مفيش تطابق بيحط NULL.
- **RIGHT JOIN**: عكس LEFT JOIN، بيرجع كل صفوف الجدول التاني (اللي بعد JOIN).
- ده أهم جزء في التعامل مع قواعد البيانات العلائقية — كل تصميم DB حقيقي هتلاقي فيه JOINs كتير.

## أخطاء شائعة
- الخلط بين `LEFT` و`RIGHT` — سهل تنسى مين الجدول "الشمال" ومين "اليمين"، افتكر إن الترتيب حسب مكان الجدول في الجملة (FROM = شمال، بعد JOIN = يمين).

## مرتبط
- [[SQL-Project-company-schema]]
- [[SQL-Functions-aggregate]]

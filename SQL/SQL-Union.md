# دمج نتائج أكتر من استعلام (UNION)

## الكود
```sql
-- قائمة بأسماء الموظفين + أسماء الفروع + أسماء العملاء في نتيجة واحدة
SELECT first_name
FROM employee
UNION
SELECT branch_name
FROM branch
UNION
SELECT client_name
FROM client;

-- قائمة بكل العملاء والموردين مع الفرع بتاعهم
SELECT client_name, branch_id
FROM client
UNION
SELECT supplier_name, branch_id
FROM branch_supplier;

-- قائمة بكل الفلوس اللي اتصرفت أو اتكسبت في الشركة
SELECT salary 
FROM employee
UNION
SELECT total_sales
FROM works_with;
```

## ملاحظات
- **مهم جدًا:** لازم عدد الأعمدة ونوع البيانات في كل استعلام يتطابقوا مع بعض، وإلا الأمر هيرفض.
- `UNION` بتشيل التكرارات تلقائيًا من النتيجة النهائية. لو عايز تحتفظ بالتكرارات، استخدم `UNION ALL`.
- مفيدة لما تيجي تجمع بيانات من جداول مختلفة في تقرير واحد.

## مرتبط
- [[SQL-Joins-inner-left-right]]

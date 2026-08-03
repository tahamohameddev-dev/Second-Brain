# دوال التجميع (COUNT / AVG / SUM / GROUP BY)

## الكود
```sql
-- عدد الموظفين
SELECT COUNT(emp_id)
FROM employee;

-- عدد الموظفات الإناث اللي اتولدوا بعد 1970
SELECT COUNT(emp_id)
FROM employee
WHERE sex = 'F' AND birth_date > '1970-01-01';

-- متوسط مرتبات الذكور
SELECT AVG(salary)
FROM employee
WHERE sex = 'M';

-- إجمالي كل المرتبات
SELECT SUM(salary)
FROM employee;

-- عدد الذكور والإناث كل واحد لوحده
SELECT COUNT(sex), sex
FROM employee
GROUP BY sex;

-- إجمالي مبيعات كل موظف مبيعات
SELECT SUM(total_sales), emp_id
FROM works_with
GROUP BY emp_id;

-- إجمالي المبيعات لكل عميل
SELECT SUM(total_sales), client_id
FROM works_with
GROUP BY client_id;
```

## ملاحظات
- `GROUP BY` بتجمع الصفوف اللي ليها نفس القيمة في عمود معين، وبعدين تطبق عليها دالة تجميع زي `COUNT`/`SUM`/`AVG`.
- من غير `GROUP BY`، الدالة زي `COUNT` أو `SUM` بتشتغل على الجدول كله كوحدة واحدة.
- الفرق بين `COUNT(*)` و`COUNT(column)`: التاني بيتجاهل القيم اللي NULL.

## مرتبط
- [[SQL-Joins-inner-left-right]]
- [[SQL-Project-company-schema]]

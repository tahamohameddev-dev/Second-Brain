# البحث بالنمط (LIKE + Wildcards)

## الكود
```sql
-- أي عميل اسمه بينتهي بـ LLC
SELECT *
FROM client
WHERE client_name LIKE '%LLC';

-- أي موظف اتولد في شهر أكتوبر (الشهر رقم 10)
SELECT *
FROM employee
WHERE birth_date LIKE '____-10%';

-- أي عميل اسمه فيه كلمة school في أي مكان
SELECT *
FROM client
WHERE client_name LIKE '%school%';
```

## ملاحظات
- `%` معناها "أي عدد من أي حروف" (حتى صفر حرف).
- `_` معناها "حرف واحد بالظبط" — استخدمناها هنا عشان نحدد شكل التاريخ (سنة-شهر-يوم).
- `%LLC` تعني: أي حاجة قبل الكلمة دي، طالما بتنتهي بـ LLC.
- `%school%` تعني: الكلمة دي في أي مكان جوه النص.

## مرتبط
- [[SQL-Basics-select-where-order-limit]]

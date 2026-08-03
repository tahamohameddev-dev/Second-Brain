# البحث عن الملفات والمحتوى (find / grep)

## الكود
```bash
# دور على كل ملفات php
find . -type f -name "*.php"

# دور على كل الملفات ما عدا ملفات php
find . -type f -not -iname "*.php"

# -iname بتدور بدون حساسية لحالة الحروف (كابتل أو سمول)
find . -type f -iname "*.php"

# دور على ملفات بصلاحيات معينة
find . -type f -perm 0664

# دور على ملفات أكبر من 1 ميجا
find . -size +1M

# دور على ملفات أصغر من 1 ميجا
find . -size -1M

# فتش عن كلمة جوه ملف معين
grep "function" filee.txt

# فتش عن كلمة في أكتر من ملف
grep "function" filee.txt taha.txt

# فتش في كل الملفات، بدون حساسية لحالة الحروف
grep -i "function" ./*

# فتش مع إظهار رقم السطر
grep -n -i "function" ./*

# ادمج find و grep مع بعض: دور على ملفات .txt وفتش جواها عن كلمة
find . -type f -iname "*.txt" -exec grep -i -n "function" {} +

# نفس الفكرة بس حدد حجم الملف كمان (أقل من 10 كيلو)
find . -type f -size -10k -iname "*.txt" -exec grep -i -n "function" {} +

# نفس الأمر، بس احفظ النتيجة في ملف بدل ما تطبعها على الشاشة
find . -type f -size -10k -iname "*.txt" -exec grep -i -n "function" {} + > ahmed.txt
```

## ملاحظات
- `find` بتدور على **الملفات نفسها** (بالاسم، الحجم، الصلاحيات...)، أما `grep` فبتدور **جوه محتوى** الملفات.
- `-exec ... {} +` هي الطريقة اللي بتخليك تشغل أمر (زي grep) على كل نتيجة رجعها find.
- `>` بتحفظ الناتج في ملف بدل ما يظهر على الشاشة (لو الملف موجود، بيتم الكتابة فوقه).

## تمرين تطبيقي كامل (سيناريو حقيقي)
```bash
sudo dnf update
sudo dnf upgrade
dnf info google-chrome-stable

sudo mkdir test_zone
cd test_zone
touch filee.txt taha.txt
echo "function hello() { return 0; }" > filee.txt
echo "this is a function too" > taha.txt

mkdir backup_dir
cp taha.txt ./backup_dir/taha_copy.txt
cp ./backup_dir/taha_copy.txt ./backup_dir/b.out

mv filee.txt file_updated.txt

sudo chown root:taha file_updated.txt
sudo chown root:root file_updated.txt
chmod 777 file_updated.txt
chmod 755 file_updated.txt
sudo chown -R taha:taha ./backup_dir

find . -type f -size -1M -iname "*.txt"
find . -perm 0755

grep "function" taha.txt
grep -n -i "function" ./*

find . -type f -size -10k -iname "*.txt" -exec grep -i -n "function" {} + > ahmed.txt

rm backup_dir/*
cd ..
rm -rf test_zone
```

## مرتبط
- [[Linux-Basics-file-operations]]
- [[Linux-Permissions-chmod-chown]]

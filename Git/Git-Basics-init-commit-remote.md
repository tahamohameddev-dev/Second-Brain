# Git - إنشاء مستودع وربطه بـ GitHub

## الكود
```bash
# إنشاء مستودع جديد
mkdir project-name
cd project-name
git init

# إضافة كل الملفات وعمل أول commit
git add .
git commit -m "Initial commit"

# ربط المستودع بـ GitHub
git remote add origin https://github.com/username/repo-name.git
git push -u origin main

# أوامر يومية سريعة
git status          # حالة الملفات دلوقتي
git log --oneline   # تاريخ الـ commits
git diff             # الفرق بين التعديلات الحالية والـ commit الأخير
```

## ملاحظات
- `git init` بيحول أي فولدر عادي لـ git repository — بيعمل فولدر مخفي `.git` جواه.
- `-u` في `git push -u origin main` بتربط الفرع المحلي بالفرع البعيد، فبعدها تقدر تكتب `git push` بس من غير ما تحدد origin/main كل مرة.
- Environment مرتبط: عمل virtual environment لمشروع بايثون:
```bash
python -m venv venv
source venv/Scripts/activate   # Windows (Git Bash)
source venv/bin/activate       # Linux/Mac
deactivate                     # للخروج من الـ venv
```

## مرتبط
- [[Git-Branching-basics]]
- [[Git-Commit-message-conventions]]

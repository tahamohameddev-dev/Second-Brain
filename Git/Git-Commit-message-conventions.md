# طريقة كتابة رسائل الـ Commit (Conventional Commits)

## الكود
```bash
git commit -m "feat: initial FastAPI project"
git commit -m "feat: add create post endpoint"
git commit -m "feat: add get post by id"
git commit -m "feat: add update post endpoint"
git commit -m "feat: add delete post endpoint"
git commit -m "fix: validate post id"
git commit -m "refactor: move helper functions"
git commit -m "docs: update README"
```

## ملاحظات
جدول البادئات (prefixes) الشائعة:

| البادئة | تستخدم لما... |
|---|---|
| `feat:` | تضيف ميزة أو endpoint جديد |
| `fix:` | تصلح حاجة كانت بايظة |
| `refactor:` | تعيد ترتيب الكود من غير ما تغير سلوكه |
| `docs:` | تعدل توثيق أو README |

الفايدة إن أي حد (أو انت نفسك بعد شهور) يقدر يفهم من الـ log بسرعة إيه اللي اتغير، من غير ما يفتح كل commit ويقرا الكود.

## مرتبط
- [[Git-Basics-init-commit-remote]]

# 🛠 Build Guide — AI Resume Screening Platform

[English](#english) · [فارسی](#فارسی) · [العربية](#العربية) · [README](./README.md)

> **Verified status:** Feature-rich demo with a broken backend requirements file

## English

### 1. Prerequisites

- React 18.2, CRA 5, Tailwind, Radix
- Flask 2.3, SQLite
- PyPDF2, python-docx
- OpenAI/Gemini integrations

Use an isolated environment or container. Prefer the committed lockfile over unconstrained upgrades.

### 2. Environment variables and services

- OPENAI_API_KEY and/or GEMINI_API_KEY
- DATABASE_URL
- Flask config

Store secrets outside Git. Use least-privilege accounts and separate development, staging and production values.

### 3. Development setup

- Remove unresolved ======= marker from backend/requirements.txt

```bash
python -m venv backend/.venv
```

```bash
pip install -r backend/requirements.txt
```

```bash
cd frontend && npm install
```

- Run backend app.py and frontend npm start

### 4. Production build

```bash
cd frontend && npm run build
```

- Use reviewed gunicorn configuration

### 5. Tests and validation

```bash
cd frontend && npm test -- --watchAll=false
```

- Test parser/redaction/scoring with synthetic resumes

### 6. Known blockers and cautions

- Requirements file contains unresolved merge separator
- Bias indicators do not guarantee fair/legal hiring

### 7. Release checklist

- Build from a clean checkout with the lockfile.
- Record runtime versions and the final artifact checksum.
- Run dependency, license and secret scanning.
- Confirm that uploaded files, fixtures and logs contain no confidential data.
- Apply migrations with a backup and tested rollback path.
- Use read-only or least-privilege credentials where possible.
- Add health checks, monitoring, backups and rollback instructions.
- Review domain obligations for medical, biometric, hiring, financial or cryptocurrency systems.

### 8. Troubleshooting

1. Confirm the current directory and runtime versions.
2. Check ports, database/queue availability and model files.
3. Inspect logs without printing tokens or passwords.
4. Reproduce from a clean virtual environment or container.
5. Do not delete lockfiles or force-upgrade packages until the original build is reproduced.
6. For repositories marked incomplete or recovery-only, complete the stated remediation before deployment.

---

## فارسی

### پیش‌نیاز و محیط

فناوری‌های بخش انگلیسی بالا پیش‌نیازهای مرجع پروژه هستند. محیط مجازی یا کانتینر جداگانه بسازید، Lockfile را حفظ کنید و کلید واقعی را داخل Git قرار ندهید.

### راه‌اندازی توسعه

دستورات بخش **Development setup** را به‌ترتیب اجرا کنید. قبل از هر دستور، مسیر جاری ترمینال، نسخه Runtime و فعال‌بودن سرویس‌های وابسته را کنترل کنید.

### Build و تست

- دستورات **Production build** را از Checkout تمیز اجرا کنید.
- تست‌ها و چک‌لیست **Tests and validation** را انجام دهید.
- نسخه ابزارها، هش خروجی و تنظیمات استقرار را ثبت کنید.
- در مخزن ناقص، ابتدا مانع مستندشده را برطرف کنید و نتیجه را دوباره اعتبارسنجی کنید.

### چک‌لیست انتشار

- اسکن Dependency، License و Secret انجام شود.
- داده شخصی، فایل آپلودی، Log و Fixture بررسی شود.
- Migration همراه Backup و Rollback آزمایش‌شده باشد.
- دسترسی‌ها حداقلی و استقرار نخست در محیط غیرعملیاتی باشد.
- مانیتورینگ، Health Check و Backup آماده باشد.

---

## العربية

### المتطلبات والبيئة

التقنيات المذكورة في القسم الإنجليزي هي المتطلبات المرجعية. استخدم بيئة معزولة أو حاوية، حافظ على ملفات القفل، ولا تضع مفاتيح حقيقية داخل Git.

### إعداد التطوير

نفذ أوامر **Development setup** بالترتيب، وتأكد من المسار وإصدارات التشغيل والخدمات التابعة قبل كل خطوة.

### البناء والاختبار

- نفذ **Production build** من نسخة نظيفة.
- شغّل **Tests and validation**.
- سجل إصدارات الأدوات وبصمة الملف الناتج وإعدادات النشر.
- في المستودعات غير المكتملة عالج العائق الموثق قبل النشر.

### قائمة الإصدار

- افحص التبعيات والتراخيص والأسرار.
- راجع البيانات الشخصية والملفات والسجلات.
- اختبر الترحيلات مع نسخة احتياطية وخطة تراجع.
- استخدم أقل صلاحيات وابدأ ببيئة غير إنتاجية.
- جهز المراقبة وفحوص الصحة والنسخ الاحتياطية.

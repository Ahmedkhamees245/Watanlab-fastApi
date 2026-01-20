# Watan Lab System — Backend (MVP)

نسخة MVP أساسية لبنية الـ backend لنظام WATAN LAB SYSTEM.

الميزات الأساسية:
- FastAPI + Pydantic
- Auth: JWT (python-jose) + bcrypt hashing (passlib)
- DB: PostgreSQL + SQLAlchemy
- Migrations: Alembic
- Docker + docker-compose (API + Postgres)
- Endpoints أساسية: signup/login، patients، orders، results
- Role-based access control (basic)

تشغيل محلي (موجز):
1. انسخ الملفات إلى مجلد المشروع.
2. أنشئ ملف `.env` من `.env.example` وغيّر القيم.
3. تشغيل: `docker-compose up --build`
4. داخل الحاوية أو محليًا: `alembic upgrade head`
5. افتح: `http://localhost:8000/docs` للـ Swagger UI

هيكلة الملفات (مبسطة):
- app/
  - main.py
  - core/ (config, security)
  - db/ (session)
  - models.py
  - schemas.py
  - crud.py
  - api/ (routes, deps)
- alembic/
- Dockerfile, docker-compose.yml, .env.example, requirements.txt

ملاحظات للأمن والخصوصية:
- احفظ المتغيرات الحسّاسة في secret manager في الإنتاج.
- استخدم HTTPS عند النشر.
- سجّل عمليات الـ audit عند تعديل بيانات المرضى والنتائج.

للمراحل القادمة (بعد MVP):
- إضافة واجهة Web/Mobile (Next.js / Flutter)
- دمج Smart Engine (خدمة مستقلة)
- الدفع، PDF/QR، SaaS multi-tenancy
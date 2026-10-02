# Darbak TPMS

تطبيق Android مستقل لمراقبة ضغط وحرارة إطارات Toyota Fortuner على شاشة السيارة.

## الحالة الحالية
**Planning / Connection Gate** — لا يبدأ بناء APK قبل حسم واختبار طريقة ربط ESP32 بشاشة Allwinner T3.

## الهدف
- أربع إطارات + الاحتياطي.
- PSI + °C + الحالة + آخر قراءة.
- مراقبة بالخلفية وتشغيل تلقائي.
- تنبيهات متدرجة وطوارئ لفقدان الضغط السريع.
- ربط Sensor ID بموقع الإطار من داخل التطبيق.
- خفيف، أوفلاين، RTL، ومصمم لـ 1024×600.

## المنصة
Android 7.1 / API 25 · Allwinner T3 / ARMv7 · RAM ~1 GB · 1024×600 Landscape · بدون Firebase.

## قاعدة أمنية
Firmware ESP32 **ليس جزءًا من هذا المستودع**. يبقى محليًا فقط على جهاز المالك ولا يُرفع إلى GitHub عامًا أو خاصًا.

راجع:
- `docs/APP_PLAN.md`
- `docs/CONNECTION_DECISION.md`
- `SECURITY.md`

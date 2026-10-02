# Connection Decision Gate

## الهدف
اختيار أبسط وأثبت وسيلة لربط ESP32 بشاشة Toyota Android.

## المرشح الأول: USB Serial
الأولوية لأنه مباشر، لا يحتاج Wi-Fi، ومناسب لتدفق TPMS الصغير.

### الاختبار الميداني المطلوب
1. تحديد USB الذي يقبل Data.
2. التأكد أن Android يرى USB-to-serial للـESP32.
3. تحديد VID/PID وUSB chipset.
4. اختبار USB permission بعد reboot.
5. Auto reconnect بعد فصل/إعادة التوصيل.
6. اختبار الاستقرار أثناء تشغيل السيارة.
7. التأكد من عدم تعارض المنفذ مع وظائف الشاشة.

## البدائل عند فشل USB
1. Bluetooth Classic.
2. Wi-Fi TCP/UDP.
3. UART داخلي فقط إذا ثبتت نقطة آمنة.

## المعمارية
ESP32 → Transport Layer → Parser/Repository → Alert Engine → UI

Transport Layer قابل للاستبدال دون إعادة كتابة التطبيق.

## معيار الاعتماد
- يعمل على T3 الفعلية.
- Auto reconnect.
- لا يحتاج تدخلًا في كل تشغيل.
- لا يعطل Wi-Fi أو وظائف الشاشة.
- latency مناسب لفقدان الضغط السريع.
- ثابت بعد reboot والفصل/إعادة التوصيل.

## الحالة
**غير محسوم بعد.**

الخطوة التالية: فحص منافذ/توصيلات الشاشة ثم اختبار USB Serial قبل بناء التطبيق الكامل.

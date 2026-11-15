Floxaap - خطوات التشغيل (مشروع Firebase: floxaap-d7a1a)

1) Firebase Console:
   - Authentication > Sign-in method > فعّل Email/Password
   - Firestore Database > Create database
   - Firestore > Rules > الصق محتوى firestore.rules كاملاً > Publish  (ضروري لتعمل الرسائل الصوتية والصور)
2) محلياً: run-Floxaap.bat  (الميكروفون يعمل على localhost)
3) النشر (مطلوب للآيفون، لأن الميكروفون يحتاج HTTPS):
   npm i -g firebase-tools ; firebase login ; firebase deploy
   ثم أضف الدومين في Authentication > Settings > Authorized domains
4) الآيفون: افتح الرابط في Safari > مشاركة > "إضافة إلى الشاشة الرئيسية".
   عند أول تسجيل صوت اسمح بالميكروفون.
ملاحظات:
- الصور تُضغط تلقائياً، والصوت حتى 90 ثانية، ويُحفظان داخل Firestore (بدون Storage).
- قيّد مفتاح الـ API بنطاقك من Google Cloud Console > Credentials.

ميزات جديدة (انشر firestore.rules مرة أخرى بعد كل تحديث):
- المكالمات الصوتية والفيديو: WebRTC بإشارات عبر Firestore. تعمل والتطبيق مفتوح فقط (الإشعارات خارج التطبيق تحتاج FCM + خادم).
  خادم TURN المجاني المضمّن للتجربة فقط؛ للإنتاج استبدل ICE في index.html بخادم TURN خاص بك (Twilio/Metered/coturn).
- علامة التوثيق: في Firestore افتح users/{uid} وأضف حقل verified (boolean) = true (من الكونسول فقط).
- القصص تختفي من العرض بعد 24 ساعة (تبقى في قاعدة البيانات ويمكنك حذفها يدوياً من وقت لآخر).

تحديث التصميم (أخضر/ذهبي):
- أُضيفت ملفات: icon-192/512.png, apple-touch-icon.png, favicon-32.png, manifest.webmanifest, firebase.json (كانت مفقودة، وبدونها لا يعمل التثبيت ولا الكاش).
- إصلاح: دالة pickH (الكاميرا/الصور في المحادثة)، وأيقونة plus.
- جديد: شريط اليوم/أمس، صور المرسلين، قائمة المحادثة، الملصقات، الموقع/الإشارة/المشاعر في النشر، فلتر فيديوهات، قصص مميزة في الملف الشخصي.
- النشر:  firebase deploy

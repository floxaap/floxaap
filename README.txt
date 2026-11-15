Floxaap - خطوات التشغيل

1) Firebase Console > مشروع floxac-f7334
   - Authentication > Get started > فعّل Email/Password
   - Firestore Database > Create database
   - Firestore > Rules > الصق محتوى firestore.rules > Publish
   - Project settings > Your apps > </> > انسخ apiKey و appId
2) افتح index.html بمحرر نصوص والصق apiKey و appId في السطر المكتوب عليه "الصق إعدادات".
3) للنشر (اختياري): npm i -g firebase-tools ثم firebase login ثم firebase deploy
   أو ارفع المجلد على Netlify. بعدها أضف الرابط في Authentication > Settings > Authorized domains.

تنبيه: لا ترفع ملف adminsdk.json مع الموقع أبداً.

ملاحظة: اسم التطبيق Floxaap، لكن معرّف مشروع Firebase يبقى floxac-f7334 (لا يمكن تغييره وهو الي يربط الموقع بقاعدة البيانات).

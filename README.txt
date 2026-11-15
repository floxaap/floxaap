Floxaap - خطوات التشغيل  (مشروع Firebase: floxaap-d7a1a)

1) Firebase Console > مشروع floxaap-d7a1a
   - Authentication > Get started > Sign-in method > فعّل Email/Password
   - Firestore Database > Create database
   - Firestore > Rules > امسح كل شي والصق محتوى firestore.rules كاملاً > Publish
     (مهم: لازم تنشر القواعد الجديدة، هي اللي تسد الثغرات)
2) إعدادات الموقع موجودة داخل index.html (CFG) - ما تحتاج تغير شي.
3) شغّل محلياً: دبل كلك على تشغيل-Floxaap.bat
4) للنشر: npm i -g firebase-tools ثم firebase login ثم firebase deploy
   أو ارفع المجلد على Netlify. بعدها أضف الدومين في Authentication > Settings > Authorized domains.

حماية إضافية مهمة:
- Google Cloud Console > APIs & Services > Credentials > مفتاح الـ API (Browser key) > Application restrictions = HTTP referrers
  وأضف دومين موقعك + localhost فقط.
- لا ترفع ملف adminsdk.json مع الموقع أبداً.

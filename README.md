# نظام البقالة المحاسبي
### Offline-First POS - يشتغل مع نت وبدون نت - كمبيوتر + جوال

**المطور:** allordziko1
**الاسم:** نظام البقالة المحاسبي
**الحالة:** v0.1 - مرحلة التأسيس

## الفكرة
- **الكمبيوتر (Tauri):** بيع مباشر Offline-First مع SQLite + مزامنة تلقائية عند وجود النت
- **الجوال (APK - Capacitor):** للمدير فقط - عرض التقارير والحركة اليومية والذمم

## التقنية المختارة (الأفضل لليمن)
- **Frontend:** React + TypeScript + Tailwind + Vite
- **Desktop:** Tauri v2 (Rust) -> ينتج .exe خفيف
- **Mobile APK:** Capacitor v6 -> ينتج .apk حقيقي من نفس كود React
- **Database Local:** SQLite (Tauri) + IndexedDB (Jawal)
- **Database Cloud Sync:** Supabase (Postgres + Realtime)
- **Offline Sync:** local-first then sync when online

## هيكلة المشروع
```
nizam-al-baqala/
├── desktop/ -> Tauri app (كاشير)
├── mobile/ -> Capacitor APK (مدير)
├── shared/ -> أنواع البيانات المشتركة
└── supabase/ -> جداول السحابة
```

## طريقة التشغيل (للمطور)
```bash
# 1- Desktop
cd desktop
npm install
npm run tauri dev

# 2- Mobile APK
cd mobile
npm install
npx cap add android
npm run build
npx cap open android  # يفتح Android Studio لبناء APK
```

## المراحل
- [x] v0.1 تصميم الواجهة (تم)
- [ ] v0.2 قاعدة البيانات المحلية + تسجيل دخول + صلاحيات
- [ ] v0.3 سلة متعددة + بحث ذكي + عبوات
- [ ] v0.4 مزامنة Supabase Offline/Online
- [ ] v1.0 APK + EXE جاهز للبيع

## الواجهة النهائية
تم تصميمها - راجع ملف design/

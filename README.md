# node-server

Node.js Server with Zoho & Twilio Integration

## 📋 وصف المشروع

خادم Node.js بسيط يوفر تكامل مع خدمتَي **Zoho** و **Twilio**. يستخدم وحدة `http` المدمجة في Node.js لإنشاء خادم ويب خفيف الوزن.

## 📁 هيكل الملفات

```
node-server/
├── server.mjs       # ملف الخادم الرئيسي (ES Module)
├── package.json     # إعدادات المشروع والمكتبات
├── .env.example     # نموذج متغيرات البيئة المطلوبة
└── README.md        # هذا الملف
```

## 🚀 كيفية التشغيل

### 1. تثبيت المتطلبات

```bash
npm install
```

### 2. إعداد متغيرات البيئة

انسخ ملف `.env.example` وأنشئ ملف `.env`:

```bash
cp .env.example .env
```

ثم عدّل الملف وأدخل بياناتك الحقيقية:

```env
PORT=3000
NODE_ENV=development

# Zoho API
ZOHO_CLIENT_ID=your_zoho_client_id
ZOHO_CLIENT_SECRET=your_zoho_client_secret
ZOHO_REFRESH_TOKEN=your_zoho_refresh_token
ZOHO_ORG_ID=your_zoho_org_id

# Twilio
TWILIO_ACCOUNT_SID=your_twilio_account_sid
TWILIO_AUTH_TOKEN=your_twilio_auth_token
TWILIO_PHONE_NUMBER=+1234567890
```

### 3. تشغيل الخادم

**تشغيل عادي:**
```bash
npm start
# أو مباشرة:
node server.mjs
```

**تشغيل مع إعادة التشغيل التلقائي عند تغيير الملفات (Development):**
```bash
npm run dev
```

بعد التشغيل، سيعمل الخادم على: **http://localhost:3000/**

## 📦 المكتبات المستخدمة

| المكتبة  | الإصدار  | الوصف                        |
|----------|----------|------------------------------|
| dotenv   | ^16.3.1  | تحميل متغيرات البيئة         |
| axios    | ^1.6.0   | طلبات HTTP                   |
| twilio   | ^4.10.0  | تكامل مع خدمة Twilio للرسائل |

## 🌿 الفروع المتاحة (Branches)

يحتوي المستودع على عدة فروع بخلاف `main`:

| الفرع                                            | الوصف                                |
|--------------------------------------------------|--------------------------------------|
| `main`                                           | الفرع الرئيسي – يحتوي الكود الأساسي  |
| `copilot/update-readme-for-node-server`          | تحديث وتوثيق README                  |
| `copilot/add-gitignore-file`                     | إضافة ملف .gitignore                 |
| `copilot/add-gitignore-file-again`               | إضافة ملف .gitignore (محاولة ثانية) |
| `copilot/add-documentation-for-enterprise-setup` | توثيق إعداد Enterprise              |
| `copilot/check-repositories-and-stars`           | فحص المستودعات والنجوم               |

> **ملاحظة:** إذا بدا المستودع "فارغاً" عند زيارته، قد يكون السبب أنك تنظر إلى فرع مختلف لا يحتوي ملفات، أو أن المستودع حديث الإنشاء. الملفات الرئيسية موجودة في فرع `main`.

## ⚙️ المتطلبات

- **Node.js** v18 أو أحدث
- **npm** v8 أو أحدث

## 📄 الرخصة

MIT © [Doldawy](https://github.com/Doldawy)

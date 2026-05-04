# node-server
Node.js Server with Zoho &amp; Twilio Integration

---

## الأسئلة الشائعة واستكشاف الأخطاء — GitHub Enterprise & Organizations

> **السيناريو:** بدأت إنشاء Enterprise أو Organization منذ نحو شهرين تقريبًا، ثم توقفت أو نسيت. بعد ذلك بحوالي شهرين (قبل يومين تقريبًا) أعدت فتح نفس الصفحة وبدأت من جديد، فظهر لك نموذج الإنشاء كأنك تبدأ من الصفر.

---

### 1. لماذا يعود نموذج الإنشاء من جديد رغم أني بدأته من قبل؟

إنشاء GitHub Enterprise أو Organization يمر بعدة خطوات (wizard). إذا أكملت جزءًا منها فقط وأغلقت المتصفح أو تركت الصفحة:

- **Enterprise:** قد تُنشأ بيانات أولية (اسم، slug) وتظهر في قائمة Enterprises حتى لو لم تُفعّل Trial بالكامل.
- **Organization:** قد تُنشأ فورًا بمجرد اختيار الاسم وتأكيده، حتى قبل إضافة الأعضاء.
- في كلا الحالين، إذا فتحت الرابط مجددًا وضغطت "New" ستبدأ **عملية إنشاء ثانية**، ولن يلغي ذلك الأولى تلقائيًا.

---

### 2. ما الفرق بين Enterprise وOrganization والـDisplay Name والـSlug؟

| المصطلح | المعنى |
|---|---|
| **Enterprise** | حساب مؤسسي (مدفوع أو Trial) يضم منظمات متعددة ويتيح سياسات مركزية وSSO. |
| **Organization (Org)** | مجموعة مستودعات وأعضاء تحت اسم موحّد — يمكن أن تكون مستقلة أو تابعة لـEnterprise. |
| **Display Name** | الاسم الذي يظهر للزوار (يمكن أن يحتوي مسافات وأحرف خاصة)، مثل: `zdoldawy 101 organization`. |
| **URL Slug / Handle** | الجزء الذي يظهر في الرابط (لا مسافات — يُستبدل بشرطة `-` عادةً)، مثل: `github.com/zdoldawy-101-organization`. |

> **مثال:** Display Name = `My Cool Org` ← Slug = `my-cool-org` ← الرابط: `https://github.com/my-cool-org`

---

### 3. كيف أتحقق مما تم إنشاؤه فعلًا؟

#### أ) صفحات الإعدادات

1. **المنظمات (Organizations):**
   افتح 👉 https://github.com/settings/organizations
   ستجد قائمة بكل المنظمات التي أنت عضو/مالك فيها.

2. **الـEnterprises:**
   افتح 👉 https://github.com/settings/enterprises
   تظهر هنا فقط الـEnterprises التي أنت **Owner** فيها.

#### ب) البريد الإلكتروني

ابحث في بريدك عن رسائل من GitHub (`noreply@github.com`) تتعلق بـ:
- `Your enterprise has been created` أو `Enterprise trial started`
- `Your organization has been created`
- أي رسالة تحتوي على اسم الـOrg أو Enterprise

#### ج) سجل المراجعة (Audit Log) — إذا كان متاحًا

إذا كنت Owner على Enterprise، يمكنك الاطلاع على:
```
https://github.com/enterprises/<enterprise-slug>/settings/audit-log
```
ابحث عن أحداث `org.create` أو `enterprise.create` لمعرفة تاريخ الإنشاء بالضبط.

---

### 4. كيف أتحقق إذا كنت كرّرت العملية (بدأت مرتين)؟

1. افتح https://github.com/settings/organizations — إذا ظهر اسمان متشابهان أو متقاربان، فأنت أنشأت منظمتين.
2. افتح https://github.com/settings/enterprises — إذا ظهر أكثر من Enterprise، فأنت كرّرت الإنشاء.
3. راجع بريدك الإلكتروني: إذا وجدت رسالتَي تأكيد في تواريخ مختلفة (مثلاً واحدة منذ شهرين وأخرى منذ يومين) فهذا تأكيد على التكرار.

---

### 5. خطوات التنظيف الآمن

#### إلغاء Trial غير المستخدمة لـEnterprise

1. انتقل إلى:
   ```
   https://github.com/enterprises/<enterprise-slug>/settings/billing
   ```
2. ابحث عن خيار **Cancel trial** أو **Cancel plan** وأكّد الإلغاء.
3. بعد الإلغاء يمكنك حذف الـEnterprise من إعدادات الـEnterprise إذا أردت.

#### حذف Organization غير مستخدمة

1. انتقل إلى صفحة الإعدادات:
   ```
   https://github.com/organizations/<org-slug>/settings/profile
   ```
2. اضغط **Delete this organization** في أسفل الصفحة وأكّد الحذف.
3. > ⚠️ **تحذير:** الحذف نهائي — تأكد أن المستودعات المهمة محفوظة في مكان آخر.

#### إزالة الأعضاء قبل الحذف (اختياري لكن مُوصى به)

1. افتح:
   ```
   https://github.com/orgs/<org-slug>/people
   ```
2. قم بإزالة الأعضاء أو نقلهم للمنظمة الصحيحة قبل الحذف، لتجنب فقدان الصلاحيات أو الإشعارات المربكة.

---

> **خلاصة:** إذا بدأت العملية منذ شهرين ثم أعدتها قبل يومين، الأرجح أنك أنشأت كيانَين منفصلَين. تحقق من الروابط أعلاه، واحتفظ بالكيان الصحيح، واحذف أو ألغِ الآخر بالخطوات المذكورة.

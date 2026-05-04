# node-server
Node.js Server with Zoho &amp; Twilio Integration

---

## 🇸🇦 ملاحظة: اسم المنظمة مقابل رابطها على GitHub

### الفرق بين Display Name و URL Slug

عند إنشاء **Organization** على GitHub، هناك قيمتان مختلفتان:

| الحقل | المعنى | مثال |
|-------|--------|------|
| **Display name** (الاسم المعروض) | الاسم الذي يراه الزوار – يمكن أن يحتوي على مسافات وأحرف خاصة | `zdoldawy 101 organization` |
| **URL slug / handle** (معرّف الرابط) | الجزء الذي يظهر في الرابط – يستبدل GitHub المسافات تلقائيًا بشرطات `-` | `zdoldawy-101-organization` |

لذلك الرابط الكامل للمنظمة سيكون:
```
https://github.com/zdoldawy-101-organization
```

> **ملاحظة:** هذا التحويل تلقائي ولا تتحكم فيه يدويًا عند الإنشاء.

---

### 🗺️ أمثلة على التحويل

| اسم المنظمة (Display Name) | الرابط المُولَّد (Slug) |
|---------------------------|------------------------|
| `My Awesome Org` | `my-awesome-org` |
| `zdoldawy 101 organization` | `zdoldawy-101-organization` |
| `Node Server Team` | `node-server-team` |

---

### 🛠️ قائمة تدقيق سريعة (Troubleshooting)

إذا لم تجد منظمتك أو لم يفتح الرابط، جرّب الخطوات التالية بالترتيب:

- [ ] **تحقق من الحساب:** تأكد أنك مسجّل دخول بالحساب الصحيح (انظر اسم المستخدم أعلى اليمين).
- [ ] **افتح صفحة المنظمات مباشرةً:**
  - <https://github.com/settings/organizations>
  - ابحث عن اسم المنظمة في القائمة، ثم انقر عليه – الرابط في المتصفح هو الـ slug الصحيح.
- [ ] **تحقق من صلاحية Owner:** صفحات Enterprise تظهر فقط للمالكين:
  - <https://github.com/settings/enterprises>
- [ ] **تأكد من الرابط الدقيق:** إذا كان اسم المنظمة يحتوي على مسافات، استبدلها بشرطات `-` في الرابط يدويًا وجرّب.
- [ ] **تحقق من الإشعارات:** ابحث في بريدك الإلكتروني عن رسائل GitHub المتعلقة بإنشاء المنظمة أو تعديلها أو حذفها.
- [ ] **إعدادات المنظمة:** بعد الدخول، يمكنك مراجعة اسم المنظمة ومعرّفها من:
  - `https://github.com/organizations/<slug>/settings/profile`

---

### 🔗 روابط مفيدة

- [صفحة المنظمات](https://github.com/settings/organizations) – عرض جميع المنظمات التي أنت عضو فيها
- [صفحة المؤسسات (Enterprise)](https://github.com/settings/enterprises) – عرض المؤسسات التي أنت مالك فيها
- [توثيق GitHub: تغيير اسم المنظمة](https://docs.github.com/en/organizations/managing-organization-settings/renaming-an-organization)

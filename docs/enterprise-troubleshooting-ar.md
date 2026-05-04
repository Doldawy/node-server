# دليل استكشاف أخطاء GitHub Enterprise وOrganization (بالعربية)

> هذا الدليل موجّه لمن يواجه تساؤلات حول إعدادات **Enterprise** و**Organization** على GitHub، وخاصةً حين تبدو الأشياء "اختفت" أو لا تظهر في المكان المتوقّع.

---

## لقطات شاشة توضيحية

فيما يلي لقطتا شاشة تمثّلان جزءًا من تفاعل GitHub Copilot مع مستودع ذي صلة:

![IMG_4665 - GitHub Copilot يعرض محتوى القسم المضاف](https://github.com/user-attachments/assets/445533ba-498f-400d-963b-645f6ea2c7fc)

![IMG_4664 - GitHub Copilot يُكمل مهمة إضافة توثيق](https://github.com/user-attachments/assets/33e3947b-e473-4748-adf7-ed05f6f58776)

---

## 1. الفرق بين Enterprise Cloud وEnterprise Server وOrganization

| المصطلح | التعريف | من يديره | أين تصل إليه |
|---|---|---|---|
| **Organization** | مجموعة من المستخدمين والمستودعات تحت اسم واحد على GitHub.com | مالك الـOrg | `https://github.com/<org-name>` |
| **Enterprise Cloud** | حساب مؤسسي يجمع عدة Organizations تحت إدارة واحدة على GitHub.com | Enterprise owner | `https://github.com/settings/enterprises` |
| **Enterprise Server (GHES)** | نسخة GitHub مثبّتة على سيرفر خاص بالشركة/الجهة | مسؤول IT أو Site Admin | رابط داخلي خاص مثل `https://github.company.com` |

### الفرق العملي بكلمات بسيطة

- **Organization** = فريق أو شركة عندهم "حساب مشترك" على موقع GitHub العادي.
- **Enterprise Cloud** = مستوى أعلى يضم عدة Organizations ويوفّر إعدادات مركزية ومتقدمة (SSO، سياسات الأمان، إلخ). يعمل على موقع GitHub.com ويحتاج اشتراكًا مدفوعًا.
- **Enterprise Server** = نسخة GitHub كاملة تعمل على سيرفر خاص داخل الشركة، لا علاقة لها بموقع GitHub.com. تحتاج تواصلًا مع مسؤول IT للحصول على رابطها.

---

## 2. أين تظهر إعدادات Enterprise ولماذا قد "تختفي" الأشياء؟

### الرابط الصحيح لإعدادات Enterprise Cloud

```
https://github.com/settings/enterprises
```

إذا دخلت هذا الرابط ولم تجد شيئًا، فذلك يعني **واحدًا** من التالي:

| السبب | التفسير | الحل |
|---|---|---|
| **تبديل الحساب** | أنت مسجّل دخولك بحساب GitHub مختلف عن الحساب المرتبط بالـEnterprise | اضغط على صورتك أعلى اليمين ← Switch account |
| **انتهاء صلاحية Trial** | تجربة الـEnterprise مدتها 30 يومًا وانتهت دون تفعيل مدفوع | راجع https://github.com/settings/billing |
| **تم حذف الـEnterprise أو الـOrg** | شخص ما (أنت أو مالك آخر) حذفه | راجع بريدك الإلكتروني لإيجاد إشعار الحذف |
| **اختلاف الـslug** | اسم الـOrg/Enterprise المُدخَل في الرابط غير صحيح | ابحث عن الاسم الحرفي الصحيح في إيميل الترحيب من GitHub |
| **الصلاحيات تغيّرت** | تمت إزالتك من دور Enterprise owner | تواصل مع مالك Enterprise آخر |

### مثال على حالة "اختفاء" Enterprise كان اسمه "zdoldawy"

إذا كنت تشاهد Enterprise باسم **zdoldawy** مع **Organization: "zdoldawy 101 organization"** ثم اختفى، جرّب:

1. افتح رابط الـOrg مباشرة: `https://github.com/zdoldawy-101-organization` (أو الاسم الحرفي كما ظهر)
2. افتح: `https://github.com/settings/enterprises` وتأكد من الحساب الصحيح
3. تحقق من البريد الإلكتروني عن أي إشعار من GitHub (إنشاء/حذف/انتهاء trial)

---

## 3. خطوات التحقق الأمني

### أ) مراجعة OAuth Apps المرتبطة بحسابك

تطبيقات مثل Auth0 أو Zoom تحصل أحيانًا على صلاحيات من خلال OAuth. راجعها هنا:

- **GitHub**: https://github.com/settings/applications
- **Google**: https://myaccount.google.com/permissions
- **Microsoft**: https://myaccount.microsoft.com/consent

> احذف أي تطبيق لا تتذكر أنك أذنت له.

### ب) مراجعة SSO (تسجيل الدخول الموحّد)

إذا كانت المؤسسة تستخدم **SAML SSO** (مثل Okta أو Azure AD)، فقد تحتاج لإعادة المصادقة للوصول إلى موارد الـOrg/Enterprise.

- من داخل إعدادات GitHub الخاصة بك: https://github.com/settings/security
- تأكد من تفعيل **Two-factor authentication (2FA)**
- راجع جلسات الجهاز النشطة: https://github.com/settings/sessions

### ج) مراجعة Audit Log (سجل المراجعة)

إذا كنت Enterprise owner، يمكنك رؤية **كل** ما حدث داخل الـEnterprise:

```
https://github.com/enterprises/<enterprise-slug>/settings/audit-log
```

أو من داخل الـOrganization:

```
https://github.com/organizations/<org-name>/settings/audit-log
```

يتيح لك الـAudit Log معرفة:
- من أنشأ الـEnterprise/Org ومتى
- من حذف مستودعًا أو أزال عضوًا
- من غيّر الإعدادات
- عنوان IP لكل إجراء

### د) التحقق من الجلسات والأجهزة النشطة

| الخدمة | الرابط |
|---|---|
| GitHub Sessions | https://github.com/settings/sessions |
| Google Device Activity | https://myaccount.google.com/device-activity |
| Microsoft Recent Activity | https://account.microsoft.com/security |

---

## 4. Troubleshooting — حل المشكلات الشائعة

### المشكلة: "لا أجد الـEnterprise في https://github.com/settings/enterprises"

1. ✅ تأكد أنك مسجّل دخولك بالحساب الصحيح (انظر اسم المستخدم أعلى الصفحة)
2. ✅ افتح نافذة Incognito وسجّل دخولك من جديد
3. ✅ راجع بريدك الإلكتروني عن رسالة من GitHub تؤكد إنشاء Enterprise
4. ✅ إذا كانت تجربة 30 يومًا انتهت، راجع صفحة الفوترة: https://github.com/settings/billing

### المشكلة: "أرى أسماء مؤسسات/فرق غريبة في شاشة تسجيل الدخول"

هذا طبيعي في حالات:
- كنت تستخدم **GitHub SSO** ببريد مؤسسة قديمة
- بريدك مربوط بـ **Google Workspace** أو **Microsoft Entra** تابعة لجهة عمل/جامعة
- كوكيز/جلسات محفوظة من تسجيلات دخول سابقة

**الحل**: امسح كوكيز المتصفح لمواقع الدخول المشكوك فيها، أو افتح نافذة Incognito.

### المشكلة: "الـOrg موجودة لكن لا أقدر أدخلها أو أشوف مستودعاتها"

- ممكن أن تكون المستودعات **Private** وصلاحياتك تغيّرت
- ممكن أن يكون الـOrg فعّل **SAML SSO** وتحتاج إعادة مصادقة: https://github.com/settings/organizations
- تأكد من دورك (Role) داخل الـOrg: Owner / Member / Outside Collaborator

---

## روابط GitHub الرسمية المفيدة

| الموضوع | الرابط |
|---|---|
| قائمة Enterprise الخاصة بك | https://github.com/settings/enterprises |
| قائمة Organizations الخاصة بك | https://github.com/settings/organizations |
| تطبيقات OAuth المصرّح لها | https://github.com/settings/applications |
| إعدادات الأمان (2FA/SSO) | https://github.com/settings/security |
| الجلسات النشطة | https://github.com/settings/sessions |
| الفوترة والاشتراكات | https://github.com/settings/billing |
| توثيق إنشاء Enterprise | https://docs.github.com/en/enterprise-cloud@latest/admin/managing-your-enterprise-account/creating-an-enterprise-account |
| توثيق Enterprise Server (GHES) | https://docs.github.com/en/enterprise-server@latest/admin |
| توثيق Audit Log | https://docs.github.com/en/organizations/keeping-your-organization-secure/managing-security-settings-for-your-organization/reviewing-the-audit-log-for-your-organization |
| توثيق SAML SSO | https://docs.github.com/en/enterprise-cloud@latest/authentication/authenticating-with-saml-single-sign-on |

---

## ملاحظة ختامية

> GitHub Copilot (أو أي مساعد ذكاء اصطناعي) **لا يملك صلاحية** إنشاء أو حذف Enterprise/Organization/Repository في حسابك. أي شيء تم إنشاؤه أو اختفى، يكون ذلك بفعلك أنت أو بفعل مالك/مسؤول آخر في نفس الـEnterprise/Org. إذا اشتبهت في نشاط غير مصرّح به، راجع الـAudit Log فورًا وغيّر كلمة المرور وفعّل 2FA.

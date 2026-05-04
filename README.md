# node-server
Node.js Server with Zoho & Twilio Integration

---

## GitHub Organization: Display Name vs. URL Slug

### Organization Display Name

The organization display name **"zdoldawy 101 organization"** is correct.
Display names on GitHub **can contain spaces, numbers, and mixed characters**.
This is the human-readable label shown in the GitHub UI.

### Organization Slug (URL handle)

The **slug** is a separate identifier used in URLs.
It **does not contain spaces** — it uses lowercase letters, numbers, and hyphens only.

Example:

| Type | Value |
|------|-------|
| Display name | `zdoldawy 101 organization` |
| URL slug (handle) | `zdoldawy` (or similar, no spaces) |
| Organization URL | `https://github.com/zdoldawy` |

---

## How to Find Your Organization URL

### Option 1 — From Personal Settings (Organizations list)

1. Go to **[https://github.com/settings/organizations](https://github.com/settings/organizations)**
2. Find your organization in the list (e.g. *zdoldawy 101 organization*).
3. Click the organization name — your browser's address bar will show the URL slug, e.g.:
   ```
   https://github.com/zdoldawy
   ```
4. That URL path segment (`zdoldawy`) is the slug you use for API calls, webhooks, and all GitHub links.

### Option 2 — From Enterprise Settings

1. Go to **[https://github.com/settings/enterprises](https://github.com/settings/enterprises)**
2. Click on your enterprise name (e.g. *zdoldawy*).
3. In the left sidebar click **Organizations** (under the enterprise menu).
4. Each organization listed shows its slug. Click an organization name to open
   `https://github.com/<org-slug>` and confirm the URL.

---

## ملاحظة توضيحية (Arabic Explanation)

**اسم المنظمة المعروض (Display Name):** `zdoldawy 101 organization`  
هذا هو الاسم الذي يظهر في واجهة GitHub وهو صحيح تمامًا.  
الأسماء المعروضة **يمكن أن تحتوي على مسافات وأرقام وأحرف مختلطة**.

**الاسم المختصر (Slug/Handle):** هو الاسم المستخدم في روابط URL ولا يحتوي على مسافات.  
مثال: `https://github.com/zdoldawy`

**كيف تجد رابط المنظمة؟**

1. افتح: [https://github.com/settings/organizations](https://github.com/settings/organizations)  
   — ستجد قائمة منظماتك. اضغط على اسم المنظمة لتفتح صفحتها وتحصل على رابطها من شريط العنوان.
2. أو افتح: [https://github.com/settings/enterprises](https://github.com/settings/enterprises)  
   — اضغط على اسم الـ Enterprise ← قسم **Organizations** في القائمة الجانبية ← اضغط على اسم المنظمة للحصول على رابطها.

# node-server
Node.js Server with Zoho &amp; Twilio Integration

---

## GitHub Organization: Display Name vs. Slug (URL Identifier)

### What is the difference?

When you create a GitHub Organization (or Enterprise), GitHub stores **two separate names**:

| | Display Name | Slug (URL identifier) |
|---|---|---|
| **What it is** | The human-readable label shown in the GitHub UI | The identifier used in all GitHub URLs |
| **Can contain spaces?** | ✅ Yes | ❌ No — uses hyphens (`-`) instead |
| **Where you see it** | Organization profile page, Enterprise dashboard | Every URL that includes the organization |
| **Example** | `zdoldawy 101 organization` | `zdoldawy-101-organization` |

> **Key point:** If the display name of your Organization contains spaces or uppercase letters, GitHub automatically replaces spaces with hyphens (`-`) and lowercases all letters to form the slug used in the URL.

---

### Display Name → Slug: Illustrative Examples

| Display Name (as shown in UI) | Slug (used in URL) |
|---|---|
| `zdoldawy 101 organization` | `zdoldawy-101-organization` |
| `My Cool Team` | `my-cool-team` |
| `Acme Corp Dev` | `acme-corp-dev` |

So if your organization is displayed as **"zdoldawy 101 organization"**, its URL will be:

```
https://github.com/zdoldawy-101-organization
```

The display name and the URL slug are **not the same** — this is expected behavior, not an error.

---

### How to Find Your Organization's URL

#### Option 1 — Via `settings/organizations`

1. Go to **[github.com/settings/organizations](https://github.com/settings/organizations)**
2. You will see a list of all organizations you belong to.
3. Each entry shows both the **display name** and, if you click on it, the **slug** used in the URL.
4. Click the organization name to go directly to its page — the URL in your browser is the organization's slug URL.

#### Option 2 — Via Enterprise Settings

1. Go to **[github.com/settings/enterprises](https://github.com/settings/enterprises)**
2. Click on your Enterprise name (e.g., `zdoldawy`).
3. In the left sidebar, click **Organizations** to see all organizations under the Enterprise.
4. Click any Organization — the URL in your browser shows the correct slug (e.g., `github.com/zdoldawy-101-organization`).

#### Option 3 — Direct URL

If you know the display name, try lowercasing it and replacing spaces with hyphens, then open:

```
https://github.com/<lowercase-display-name-with-hyphens>
```

Example:

```
https://github.com/zdoldawy-101-organization
```

---

### Why Does the Name Look Different from the URL?

This is a common source of confusion. GitHub allows organization owners to set a **friendly display name** (which can include spaces, capital letters, and special characters). However, URLs on the web cannot contain spaces, so GitHub derives a **slug** from the original name chosen at creation time (spaces become hyphens, letters are lowercased).

Think of it like this:
- **Display name** = the sign on the front door (can say anything)
- **Slug** = the street address (must follow strict rules, no spaces)

Both refer to the **same organization** — nothing has disappeared.

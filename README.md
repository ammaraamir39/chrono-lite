# 🕒 nanochrono

[![npm
version](https://img.shields.io/npm/v/nanochrono.svg?style=flat-square)](https://www.npmjs.com/package/nanochrono)
[![install
size](https://img.shields.io/bundlephobia/min/nanochrono?style=flat-square)](https://bundlephobia.com/result?p=nanochrono)
[![npm
downloads](https://img.shields.io/npm/dm/nanochrono.svg?style=flat-square)](https://www.npmjs.com/package/nanochrono)
[![license](https://img.shields.io/npm/l/nanochrono.svg?style=flat-square)](https://github.com/ammaraamir39/nanochrono/blob/main/LICENSE)

**nanochrono** is an **ultra-lightweight (\<500B)** human-readable time
formatter for modern JavaScript apps.

It converts timestamps into friendly phrases like:

    1 minute ago
    3 hours ago
    yesterday
    in 2 days

Built for the **modern web**, nanochrono uses the native
**Intl.RelativeTimeFormat** API, giving you **built-in
internationalization with zero extra bundle size**.

---

# ✨ Features

### 🪶 Ultra Tiny

Less than **500 bytes minzipped**.

### 🌍 Native Internationalization

Supports **100+ languages** via built-in `Intl` APIs.

### 🚀 Zero Dependencies

No dependency tree, no vulnerabilities, no supply chain risk.

### 🛡️ Type Safe

Written in **TypeScript** with full typings and autocomplete.

### ⚡ Edge Runtime Ready

Works perfectly with:

- Vercel Edge Functions
- Cloudflare Workers
- Deno
- Bun
- Node.js
- Browsers

---

# 📦 Installation

```bash
npm install nanochrono
```

or

```bash
pnpm add nanochrono
```

or

```bash
yarn add nanochrono
```

---

# 🚀 Quick Start

```ts
import { formatRelative } from "nanochrono"

// 1 minute ago
formatRelative(Date.now() - 60000)

// 2 hours ago
formatRelative(Date.now() - 7200000)

// yesterday
formatRelative(Date.now() - 86400000)
```

---

# 🌍 Internationalization

nanochrono automatically supports **any locale supported by the
JavaScript runtime**.

```ts
import { formatRelative } from "nanochrono"

// Spanish
formatRelative(Date.now() - 3600000, "es")
// "hace 1 hora"

// French
formatRelative(Date.now() - 172800000, "fr")
// "avant-hier"

// Japanese
formatRelative(Date.now() - 60000, "ja")
// "1分前"
```

No locale files required.\
No additional imports.

---

# 📖 API

## formatRelative(date, locale?)

Formats a date or timestamp into a **human-readable relative time
string**.

### Parameters

---

Parameter Type Description

---

date Date \| number Date object or timestamp
(milliseconds)

locale string Optional BCP-47 locale
(e.g. "en", "fr", "es").
Defaults to "en"

---

### Returns

    string

Example:

```ts
formatRelative(Date.now() - 60000)
// "1 minute ago"
```

---

# 📊 Size Comparison

Library Minified Size Dependencies

---

Moment.js \~67 KB many
Day.js \~7 KB plugins
date-fns \~20 KB many
**nanochrono** **\<500B** **0**

Perfect for **performance-focused applications**.

---

# 🧠 Why nanochrono?

Traditional date libraries ship **large locale dictionaries**.

Example:

    moment/locale/fr.js
    moment/locale/es.js
    moment/locale/ja.js

Each language adds extra **kilobytes** to your bundle.

But **modern JavaScript runtimes already include these translations**
via the `Intl` API.

nanochrono simply **uses what already exists in the runtime**, meaning:

✔ no locale imports\
✔ no bundle growth\
✔ instant global language support

---

# 🧩 Example Use Cases

### Social feeds

    5 minutes ago
    2 hours ago
    yesterday

### Notifications

    just now
    1 minute ago
    3 days ago

### Messaging apps

    last seen 2 minutes ago
    sent 3 hours ago

### Activity logs

    updated 1 day ago
    created 2 weeks ago

---

# ⚡ Edge & Serverless Friendly

nanochrono is ideal for modern runtimes:

Runtime Supported

---

Node.js ✅
Browser ✅
Deno ✅
Bun ✅
Cloudflare Workers ✅
Vercel Edge ✅

---

# 🛠 Example Integration

### React

```tsx
import { formatRelative } from "nanochrono"

export default function Post({ createdAt }) {
  return <span>{formatRelative(createdAt)}</span>
}
```

### Express API

```ts
res.json({
  created: formatRelative(user.createdAt)
})
```

---

# 📜 License

MIT © Ammar Aamir

---

# ⭐ Support the Project

If you like **nanochrono**, please consider:

- ⭐ Starring the repository
- 🐛 Reporting issues
- 💡 Suggesting improvements

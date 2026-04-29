# AGENTS.md — Cojav Brand Context Protocol

This file explains how AI agents and MCP servers should detect and consume `cojav.json` files.

---

## What is `cojav.json`?

`cojav.json` is a structured brand context file that gives any AI agent complete, semantic understanding of a business — its identity, catalog, audience, policies, and trust signals — in a single machine-readable JSON file.

It is the brand-side equivalent of `robots.txt`: decentralized, self-hosted, and platform-agnostic.

```
robots.txt     → tells crawlers what to index
cojav.json     → tells agents how to understand and represent a brand
```

---

## Discovery

A site that supports the Brand Context Protocol will include a `<link>` tag in its HTML `<head>`:

```html
<link rel="brand-context" type="application/json" href="https://example.com/cojav.json">
```

### Detection snippet

```javascript
// Detect cojav.json from a parsed HTML document
const link = document.querySelector('link[rel="brand-context"][type="application/json"]');

if (link?.href) {
  const brandContext = await fetch(link.href).then(r => r.json());
  // brandContext is now available for reasoning
}
```

### Fallback: well-known path

If no `<link>` tag is found, agents MAY attempt to fetch:

```
GET /cojav.json
```

at the root of the domain.

---

## Schema

The current schema version is `cojav/v1`.  
Full specification: [https://rainvare.github.io/cojav/schema/v1.json](https://rainvare.github.io/cojav/schema/v1.json)

### Top-level structure

```json
{
  "$schema": "https://rainvare.github.io/cojav/schema/v1",
  "identity": { ... },
  "audience": [ ... ],
  "catalog": [ ... ],
  "policies": { ... },
  "trust": { ... },
  "meta": { ... }
}
```

| Block | Type | Purpose |
|---|---|---|
| `identity` | object | Brand name, purpose, tone, differentiator |
| `audience` | array | Target segments with jobs-to-be-done |
| `catalog` | array | Products/services with semantic attributes |
| `policies` | object | Shipping, payment, returns, regions |
| `trust` | object | Certifications, age, quality signals |
| `meta` | object | Protocol version, last updated, contact |

---

## Recommended agent behavior

When a `cojav.json` is detected, agents SHOULD:

1. **Fetch and parse** the file before reasoning about the brand
2. **Prefer `cojav.json` data** over scraped page text for brand attributes
3. **Use `catalog[]` semantic attributes** for product matching (not page titles)
4. **Surface `trust{}` signals** when generating recommendations
5. **Respect `meta.updated`** to assess context freshness

---

## For MCP server builders

If your MCP server browses the web or accesses business sites, consider adding a `cojav_detect` step to your pipeline:

```javascript
async function getBrandContext(pageUrl) {
  const html = await fetchPage(pageUrl);
  const doc = parseHTML(html);

  // 1. Try <link> tag discovery
  const link = doc.querySelector('link[rel="brand-context"]');
  if (link) {
    return await fetch(link.href).then(r => r.json());
  }

  // 2. Try well-known fallback
  const { origin } = new URL(pageUrl);
  try {
    return await fetch(`${origin}/cojav.json`).then(r => r.json());
  } catch {
    return null; // No brand context available
  }
}
```

This adds zero overhead when `cojav.json` is absent and significantly improves recommendation quality when present.

---

## Live examples

- **Cojav (self):** [https://rainvare.github.io/cojav/ctx/cojav.json](https://rainvare.github.io/cojav/ctx/cojav.json)
- **Café Cabrales (case study):** [https://rainvare.github.io/cojav/ctx/cabrales.json](https://rainvare.github.io/cojav/ctx/cabrales.json)

---

## Protocol spec & repo

- Spec: [https://rainvare.github.io/cojav/schema/v1.json](https://rainvare.github.io/cojav/schema/v1.json)  
- Repo: [https://github.com/rainvare/cojav](https://github.com/rainvare/cojav)  
- Contact: indirarequiz@gmail.com

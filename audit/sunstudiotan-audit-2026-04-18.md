# Website Audit: Sun Studio Tan (`sunstudiotan.com`)

**Audit date:** 2026-04-18 (UTC)  
**Audited pages:**
- `/` (homepage)
- `/book`
- `/pricing`
- `/about-us`

## Scope and method
This is a live-content, manual audit based on publicly rendered page output available in this environment. It focuses on:
- UX/content quality
- SEO/content structure
- accessibility and technical signals visible in rendered output

> Note: Direct network header inspection tools (e.g., `curl -I`) were blocked in this runtime, so security/header checks are limited.

---

## Executive summary
Sun Studio Tan has strong local intent messaging and clear service differentiation (Base/Build/Bronzed), but it currently has **high-impact technical SEO and content quality gaps** that may hurt discoverability and trust:

1. **Missing/weak metadata signals** (no detected meta description; no detected structured data).
2. **Heading and content-structure issues** (placeholder/invalid heading content and repeated sections).
3. **Copy-quality issues on key pages** (typos/formatting artifacts and grammar errors).
4. **Accessibility fragility** (script-injected fallback H1 strongly suggests semantic structure may not be robust).

---

## Findings by priority

## P0 (Critical)

### 1) Semantic heading structure appears fragile (H1 fallback injected by script)
- A script at the bottom of pages injects an H1 if one is missing.
- This pattern indicates the page may not reliably output a native semantic H1 in all render contexts.

**Why it matters:** Inconsistent heading semantics can reduce SEO clarity and degrade screen-reader navigation.

**Recommended fix:**
- Ensure each page has one explicit, server-rendered `<h1>` matching page intent.
- Keep script-based fallback only as defense-in-depth, not primary behavior.

---

## P1 (High)

### 2) No detected meta description on homepage output
- `meta name="description"` was not found in rendered output scan.

**Why it matters:** Search snippets may be auto-generated and less compelling; CTR often suffers.

**Recommended fix:**
- Add unique meta descriptions for homepage and top landing pages (`/pricing`, `/book`, `/about-us`, major service pages).
- Keep 140–160 characters, include Columbus/local intent naturally.

### 3) No detected structured data (`application/ld+json`) in homepage output
- No JSON-LD was detected.

**Why it matters:** Missing business/service schema can limit rich result eligibility and local knowledge reinforcement.

**Recommended fix:**
- Add JSON-LD for `LocalBusiness`/`BeautySalon` with:
  - Name, address, phone, geo, openingHours, sameAs
  - Service catalog (spray tan, LED teeth whitening)
  - AggregateRating (if policy-compliant)

### 4) Broken/placeholder-looking section content on homepage
- A heading appears as `## ?` and there are signs of noisy sectioning.

**Why it matters:** Lowers perceived quality and may confuse search engines parsing topical hierarchy.

**Recommended fix:**
- Remove placeholder headings/content artifacts.
- Rebuild homepage section hierarchy with clean H2/H3 outline.

---

## P2 (Medium)

### 5) Content duplication and overlong homepage narrative
- Similar service messaging is repeated across multiple blocks (e.g., spray tan levels and repeated service explainer sections).

**Why it matters:** Dilutes topical focus, reduces scanability, and can suppress conversion on mobile.

**Recommended fix:**
- Consolidate repeated blocks.
- Keep one core “How it works + pricing tiers” section, then link to details.

### 6) Copy and polish issues on trust-critical pages
Examples observed:
- “7 Days a a Week” (grammar error)
- “Wana Glow & Stay in the Know???” (spelling/tone inconsistency)
- “Monthly M embership” (formatting artifact)
- Literal heading artifact: “H2: LED Teeth Whitening — Powered by Bleach Bright”

**Why it matters:** Quality errors reduce conversion trust, especially for first-time clients.

**Recommended fix:**
- Run a copy QA pass for all transactional pages.
- Establish style guide for capitalization, punctuation, and CTA tone.

### 7) Navigation/content consistency opportunities
- Page templates vary significantly (e.g., `/pricing` mostly image-driven vs. content-rich pages).

**Why it matters:** Inconsistent UX can create friction and indexing imbalance between pages.

**Recommended fix:**
- Standardize page template components: intro paragraph, benefits, FAQs, primary CTA, internal links.

---

## P3 (Low)

### 8) Improve conversion instrumentation and proof architecture
- Review proof is present, but could be made more structured and distributed near key CTAs.

**Recommended fix:**
- Add testimonials/review snippets adjacent to booking buttons.
- Add event-specific landing pages (weddings, formals, vacations) with unique proof and FAQs.

---

## 30-day action plan

### Week 1
- Fix heading integrity (real H1s on all key pages).
- Remove placeholder/invalid headings.
- Correct copy errors on homepage and `/book`.

### Week 2
- Add unique meta titles/descriptions site-wide for top pages.
- Implement JSON-LD LocalBusiness schema.

### Week 3
- De-duplicate homepage sections.
- Standardize pricing and service page structure.

### Week 4
- Add internal links between service pages and FAQs.
- Add conversion tracking checkpoints (Book CTA clicks by page/section).

---

## Quick wins checklist
- [ ] Native `<h1>` on every key page
- [ ] Meta description for each indexable page
- [ ] JSON-LD LocalBusiness schema
- [ ] Remove placeholder heading (`?`) and formatting artifacts
- [ ] Copy QA for grammar/spelling consistency
- [ ] Compress homepage copy into clearer sections with stronger CTA rhythm


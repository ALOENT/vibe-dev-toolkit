<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f172a,50:1e3a5f,100:0ea5e9&height=200&section=header&text=Vibe%20Dev%20Toolkit&fontSize=52&fontColor=ffffff&fontAlignY=38&desc=Build%20%E2%86%92%20Secure%20%E2%86%92%20SEO%20%E2%86%92%20Launch&descAlignY=58&descSize=18&descColor=94a3b8" width="100%"/>

<br/>

[![Made for Vibecoders](https://img.shields.io/badge/Made%20for-Vibecoders-0ea5e9?style=for-the-badge&logo=rocket&logoColor=white)](.)
[![Prompts Included](https://img.shields.io/badge/Copy--Paste%20Prompts-15%2B-34d399?style=for-the-badge&logo=openai&logoColor=white)](.)
[![Zero Fluff](https://img.shields.io/badge/Zero%20Fluff-100%25-a78bfa?style=for-the-badge&logo=checkmarx&logoColor=white)](.)

<br/>

> **Everything a modern AI-assisted developer needs — in the exact order you'll actually use it.**  
> No theory. Just copy-paste prompts, checklists, and workflows that work.

<br/>

</div>

---




## 💡 Why This Exists

**I spent way too long figuring out the right *order* to do all of this.**

**Most vibe coding guides give you tools. Nobody tells you **when** to use them.
This repo is my attempt to fix that — everything I learned about shipping an
AI-assisted project properly, arranged in the sequence that actually makes sense.**

***If you're building something with Antigravity, Cursor, Lovable, Bolt, or any AI tool —
this is the checklist I wish I had on day one.***

---

<div align="center">

## 🗺️ The Sequence

*Most vibecoders do this in the wrong order. Here's the right one.*

</div>

<br/>

```
┌──────────────────────────────────────────────────────────────────────────┐
│                                                                          │
│   🏗️  BUILD        🔒  SECURE       🔍  SEO         🚀  LAUNCH         │
│   Codvyn           Security         AI Website      Pre-Launch           │
│   Workflow    →    Audit       →    Setup      →    Checklist            │
│                                                                          │
│                              🐛  DEBUG (ongoing)                         │
│                                                                          │
└──────────────────────────────────────────────────────────────────────────┘
```

<br/>

---

<div align="center">

# Phase 01 — Build Your UI

### *The Codvyn Workflow*

<img src="https://img.shields.io/badge/Antigravity-Browser%20Agent-22d3ee?style=flat-square&logo=googlechrome&logoColor=white"/>
<img src="https://img.shields.io/badge/Claude-Prompt%20Refiner-a78bfa?style=flat-square&logo=anthropic&logoColor=white"/>
<img src="https://img.shields.io/badge/Stitch-UI%20Builder-34d399?style=flat-square&logo=google&logoColor=white"/>

</div>

<br/>

> Steal the *look* of any website you love. Apply it to your own idea. Zero manual design work.

```
┌─────────────────┐      ┌─────────────────┐      ┌─────────────────┐
│                 │      │                 │      │                 │
│  ANTIGRAVITY    │ ───▶ │     CLAUDE     │ ───▶ │    STITCH       │
│  Browser Agent  │      │  Prompt Refiner │      │   UI Builder    │
│                 │      │                 │      │                 │
│ Visits your     │      │ Extracts visual │      │ Builds the      │
│ design ref URL  │      │ DNA + refines   │      │ full UI for you │
│                 │      │ your raw idea   │      │                 │
└─────────────────┘      └─────────────────┘      └─────────────────┘
```

<br/>

### ⚡ Step 1 — Enable Browser in Antigravity

1. Open **Settings** → **Integrations** → **Browser Tools**
2. Toggle **Enable Browser** → ON
3. Enable all three permissions: `Screenshot capture` · `DOM inspection` · `External URL access`
4. Test with this:

```
Visit https://stripe.com and take a full-page screenshot
```

✅ If a snapshot appears — you're good.

<br/>

### ⚡ Step 2 — Connect Stitch via MCP

**In Antigravity → Settings → MCP Connections → Add New:**

| Field | Value |
|---|---|
| Name | Stitch UI Builder |
| URL | `https://stitch.googleapis.com/mcp` |
| Protocol | MCP v1 |
| Auth | API Key |

**MCP config format (Claude Desktop / Cursor style):**

```json
{
  "mcpServers": {
    "stitch": {
      "serverUrl": "https://stitch.googleapis.com/mcp",
      "headers": {
        "X-Goog-Api-Key": "YOUR_API_KEY_HERE"
      }
    }
  }
}
```

Get your Stitch API key at → [stitch.withgoogle.com](https://stitch.withgoogle.com) → Account → API Access

> ⚠️ MCP support in Stitch is evolving. Always check [codvyn.in](https://codvyn.in) for the latest setup steps.

**Verify:** Type `@Stitch create a simple card component with a purple button` — renders = fully connected ✅

### ⚡ Step 3 — The Master Prompt

> Fill 2 placeholders → paste into Claude → get a production-ready Stitch prompt back.

| Placeholder | What to put |
|---|---|
| `{DESIGN_REFERENCE_LINK}` | URL of a site whose *look* you want (linear.app, vercel.com, stripe.com) |
| `{RAW_PROMPT}` | Your rough idea — write it however you like |

```
Design Reference Link: {DESIGN_REFERENCE_LINK}

You are a senior UI/UX engineer and prompt architect. Your job is to
transform the inputs given to you into a single, exhaustive,
production-ready prompt for a vibe coding tool (Stitch). Follow these
permanent rules without exception:

1. DESIGN REFERENCE ANALYSIS — Visit the design reference link provided.
   Extract ONLY visual information: color palette (exact hex values if
   possible), typography style, spacing and layout patterns, component
   styles (buttons, cards, navbars), animation/interaction feel, overall
   aesthetic mood. Do NOT extract any content, copy, or functional ideas
   from the reference. It is a visual bible only.

2. IDEA SOURCE — The website concept, purpose, features, pages, and
   functionality come EXCLUSIVELY from the raw prompt. Do not let the
   design reference influence what the website does or contains.

3. OUTPUT FORMAT — Produce one single refined prompt in this order:
   a. Project Overview (from raw prompt only)
   b. Visual Language (from design reference only)
   c. Page-by-Page UI Plan (sections, components, layout per page)
   d. Component Specs (buttons, typography scale, color tokens, spacing)
   e. Build Instructions for Stitch (step-by-step, start building now)

4. Be specific, not vague. No placeholders in output. Every color, font
   style, and spacing decision must be explicitly defined.

5. End with: "Now analyze the design reference link visually, then begin
   building the UI in Stitch immediately without asking any clarifying
   questions."

Raw Prompt: {RAW_PROMPT}
```

<br/>

### 🔄 Full Workflow at a Glance

```
01  Paste master prompt into Claude
    └─ Fill design URL + your raw idea

02  Claude refines it
    └─ Returns detailed, structured, Stitch-ready prompt

03  Paste into Antigravity
    └─ Tell it: "start building and follow Codvyn"

04  Antigravity browses the reference
    └─ Extracts colors, fonts, spacing via browser

05  Sends to Stitch via MCP
    └─ Stitch builds your UI — full visual control

06  Review & iterate
    └─ Request tweaks directly in Antigravity chat
```

<br/>

---

<div align="center">

# Phase 02 — Visualize Your Architecture

### *Map your system before writing a single backend line*

<img src="https://img.shields.io/badge/Output-Standalone%20HTML%20File-fbbf24?style=flat-square"/>
<img src="https://img.shields.io/badge/Style-Dark%20Theme%20SVG-1e293b?style=flat-square"/>

</div>

<br/>

### 🎨 Color System

| Component | Fill | Stroke |
|---|---|---|
| 🔵 Frontend | `rgba(8, 51, 68, 0.4)` | `#22d3ee` cyan |
| 🟢 Backend | `rgba(6, 78, 59, 0.4)` | `#34d399` emerald |
| 🟣 Database | `rgba(76, 29, 149, 0.4)` | `#a78bfa` violet |
| 🟡 AWS/Cloud | `rgba(120, 53, 15, 0.3)` | `#fbbf24` amber |
| 🔴 Security | `rgba(136, 19, 55, 0.4)` | `#fb7185` rose |
| 🟠 Message Bus | `rgba(251, 146, 60, 0.3)` | `#fb923c` orange |
| ⚪ External | `rgba(30, 41, 59, 0.5)` | `#94a3b8` slate |

<br/>

### 📋 Diagram Prompt

```
You are a senior software architect. Generate a professional dark-themed
architecture diagram as a self-contained HTML file with inline SVG.

System to diagram: [DESCRIBE YOUR SYSTEM HERE]

Requirements:
- Font: JetBrains Mono throughout
- Background: #020617 with subtle grid (stroke #1e293b, 40x40 pattern)
- Color-code all components by type:
    Frontend=cyan (#22d3ee), Backend=emerald (#34d399),
    Database=violet (#a78bfa), Cloud=amber (#fbbf24),
    Security=rose (#fb7185), MessageBus=orange (#fb923c)
- Rounded rects (rx=6), 1.5px stroke, semi-transparent fills
- Draw ALL arrows BEFORE component boxes (z-order matters)
- Add opaque backing rect (#0f172a) behind each component to mask arrows
- Security groups: stroke-dasharray="4,4", rose color
- Region boundaries: stroke-dasharray="8,4", amber, rx=12
- Legend placed OUTSIDE all boundary boxes
- 3 summary cards below diagram + minimal footer
- Single self-contained .html — no external CSS or JS

Output only the complete HTML. Nothing else.
```

> 💡 The generated HTML opens directly in any browser — share as a static file or embed in docs.

<br/>

---

<div align="center">

# Phase 03 — Security Audit

### *Vibe coding is fast. Security bugs are forever.*

<img src="https://img.shields.io/badge/Run%20This-Before%20Every%20Deploy-fb7185?style=flat-square&logo=shield&logoColor=white"/>

</div>

<br/>

### 🛡️ Global Security System Prompt

> Set this in `.cursorrules` or as custom system instructions **before you start coding.**

```
You are an expert, security-conscious senior developer. While writing code,
you must prioritize security over speed. Never hardcode API keys or secrets.
Always validate and sanitize user input. Prefer established managed services
(like Supabase/Firebase) over custom authentication. Flag any potentially
insecure architectural decisions before writing the code.
```

<br/>

### 🔍 Audit Prompts — Run One by One

<details>
<summary><b>1. 🔑 Find Leaked Secrets</b></summary>

<br/>

```
@codebase Scan all frontend and client-side files for hardcoded API keys,
secrets, or tokens. If found, refactor the code to fetch these securely
from the server using environment variables.
```

</details>

<details>
<summary><b>2. 💉 XSS & SQL Injection Check</b></summary>

<br/>

```
Review all API controllers and database queries. Identify any areas where
user input is executed or saved without sanitization or parameterization.
Rewrite these sections to strictly prevent SQL injection and XSS.
```

</details>

<details>
<summary><b>3. 🚦 Rate Limiting</b></summary>

<br/>

```
Analyze my API routes, specifically the endpoints that interact with external
AI models (like OpenAI or Gemini). Implement a robust rate-limiting middleware
to prevent scraping, bot attacks, and API billing abuse.
```

</details>

<details>
<summary><b>4. 🔐 Auth Architecture Review</b></summary>

<br/>

```
Review my current authentication implementation. If there is any custom-rolled
session management or password hashing, provide a migration plan to replace it
with a secure, pre-built solution like Supabase, Clerk, or Firebase Auth.
```

</details>

<details>
<summary><b>5. 🔢 API Versioning</b></summary>

<br/>

```
Review my current API routing structure. Refactor the routes to implement
standard API versioning (e.g., prepending /api/v1/ to the endpoints) while
ensuring no existing internal logic breaks.
```

</details>

<details>
<summary><b>6. 📁 File Upload Security</b></summary>

<br/>

```
Audit the file upload logic in the codebase. Ensure strict server-side
validation for MIME types and maximum file size limits. Confirm that uploaded
files are stored in a non-executable directory and cannot overwrite system files.
```

</details>

<details>
<summary><b>7. 📦 Dependency Audit</b></summary>

<br/>

```
Review my package.json [or requirements.txt / pom.xml]. Identify any libraries
that are known to be insecure, unmaintained, or redundant. Suggest secure,
well-maintained alternatives.
```

</details>

<br/>

---

<div align="center">

# Phase 04 — SEO Setup

### *80% of vibecoders ship their site and get zero traffic.*
### *The reason is always the same: no SEO.*

<img src="https://img.shields.io/badge/Google-Wants%20Signals-ea4335?style=flat-square&logo=google&logoColor=white"/>
<img src="https://img.shields.io/badge/You-Ship%20the%20Signals-34d399?style=flat-square"/>

</div>

<br/>

### ❌ What AI Websites Get Wrong

| Mistake | Google Impact |
|---|---|
| No `<title>` tag | Doesn't know your page's name |
| No meta description | Search snippet missing → fewer clicks |
| Everything in `<div>`, no H1/H2 | Can't understand your structure |
| No alt text on images | Images invisible to search engines |
| No `sitemap.xml` | Can't find your pages |
| Slow load speed | Ranking drops automatically |

<br/>

### 🏗️ Heading Structure — Copy This Pattern

```html
<h1>Best Web Designer in Delhi</h1>   <!-- ONE per page only -->
  <h2>Our Services</h2>
    <h3>Logo Design</h3>
    <h3>Mobile App UI</h3>
  <h2>Why Choose Us</h2>
```

<br/>

### 📄 Complete `<head>` Template

```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Best Web Designer in Delhi | YourBrand</title>
  <meta name="description" content="Professional web design in Delhi. Fast, SEO-friendly websites. Call now!">
  <meta name="robots" content="index, follow">
  <link rel="canonical" href="https://yourdomain.com/">
  <meta property="og:title" content="Best Web Designer in Delhi">
  <meta property="og:image" content="https://yourdomain.com/og.jpg">
</head>
```

<br/>

### 🗺️ sitemap.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url><loc>https://yourdomain.com/</loc><priority>1.0</priority></url>
  <url><loc>https://yourdomain.com/about</loc><priority>0.8</priority></url>
  <url><loc>https://yourdomain.com/services</loc><priority>0.8</priority></url>
  <url><loc>https://yourdomain.com/portfolio</loc><priority>0.7</priority></url>
  <url><loc>https://yourdomain.com/contact</loc><priority>0.6</priority></url>
</urlset>
```

### 🤖 robots.txt

```
User-agent: *
Allow: /
Disallow: /admin/
Sitemap: https://yourdomain.com/sitemap.xml
```

<br/>

### 🏆 LocalBusiness Schema (Boosts CTR by 20–30%)

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "LocalBusiness",
  "name": "Your Business Name",
  "description": "Short description of your services",
  "url": "https://yourdomain.com",
  "telephone": "+91-XXXXXXXXXX",
  "address": {
    "@type": "PostalAddress",
    "addressLocality": "Delhi",
    "addressCountry": "IN"
  },
  "sameAs": ["https://instagram.com/youraccount"]
}
</script>
```

> Validate at → [search.google.com/test/rich-results](https://search.google.com/test/rich-results)

<br/>

### ⚡ Page Speed Fixes

| Fix | Tool | Gain |
|---|---|---|
| Convert images to WebP | [squoosh.app](https://squoosh.app) | 40–70% smaller |
| Add lazy loading | `loading="lazy"` attribute | Faster initial load |
| Remove unused CSS | PurgeCSS / DevTools | 60%+ CSS reduction |
| Minify JS and CSS | AI builder settings | 10–30% faster |
| Use a CDN | Cloudflare Free Plan | Global speed boost |

<br/>

### 🤖 SEO Master Prompt

```
You are an expert SEO specialist. I have an AI-generated website about:
[YOUR WEBSITE DESCRIPTION]

Generate complete, production-ready SEO code including:
1. Full <head> section — title, meta description, viewport, robots, canonical, og tags
2. Proper H1, H2, H3 heading structure for: Hero, Services, About, Portfolio, Contact
3. sitemap.xml with 5 core pages
4. robots.txt file
5. Alt text for 5 images
6. JSON-LD Schema markup for LocalBusiness

Target keyword: [YOUR MAIN KEYWORD]
Location: [YOUR CITY]
Business Name: [YOUR BRAND NAME]

Give me everything ready to copy-paste. No explanations — just the code.
```

> ⚠️ Replace everything in `[ ]` with your actual info before pasting.

<br/>

---

<div align="center">

# Phase 05 — Pre-Launch Checklist

### *Product is built. Code is clean. SEO is set.*
### *This is the final gate before you go live.*

</div>

<br/>

### ⚖️ Legal & Compliance
- [ ] Privacy Policy page live
- [ ] Terms & Conditions live
- [ ] Cookie consent banner (required for EU/GDPR)

### 🔐 Auth & Security
- [ ] Signup / login flow tested end-to-end
- [ ] Email verification working
- [ ] Password reset flow tested
- [ ] OAuth (Google, GitHub, etc.) working if included
- [ ] Rate limiting active on auth endpoints

### 💳 Payments
- [ ] Payment flow tested — success AND failure cases
- [ ] Upgrade flow works
- [ ] Downgrade flow works
- [ ] Cancel flow works
- [ ] Webhook handling for payment events

### 📊 Analytics
- [ ] User event tracking set up (PostHog / Mixpanel / Amplitude)
- [ ] Page view tracking active
- [ ] Google Analytics connected

### 🔍 SEO & Visibility
- [ ] Website submitted to Google Search Console
- [ ] sitemap.xml submitted
- [ ] Submitted to Bing Webmaster Tools
- [ ] PageSpeed score 70+ on mobile

### 💬 Support & Polish
- [ ] Contact / support email working
- [ ] Bug report option visible
- [ ] Custom 404 page created
- [ ] Favicon added
- [ ] All broken links fixed

<br/>

---

<div align="center">

# Phase 06 — Debug Like a Senior Dev

### *You will hit bugs. This prompt gets you to root cause in one shot.*

<img src="https://img.shields.io/badge/Copy%20This%20Prompt-Save%20It%20Forever-fbbf24?style=flat-square"/>

</div>

<br/>

> Most people describe their bug wrong. This structure forces you to give Claude exactly what it needs — and forces it to give you exactly what you need back.

```
I have a bug. Here's everything you need:

**Error message:**
[paste the full error / stack trace]

**What I was trying to do:**
[one sentence — what should this code do]

**Relevant code:**
[paste only the function/block where the error happens]

**What I already tried:**
[list 2–3 things you attempted]

Now do this:
1. Identify the exact cause in one sentence
2. Show me the fixed code
3. Tell me why I missed it — what pattern should I look for next time
```

> Point #3 is what separates junior debugging from senior debugging.  
> Fix the bug today. Understand the pattern. Never hit it again.

<br/>

---

<div align="center">

## 🗂️ Repo Structure

</div>

```
vibe-dev-toolkit/
│
├── 📁 architecture-diagram/
│   ├── SKILL.md                    # Diagram skill instructions
│   └── assets/template.html        # Base HTML template
│
├── 📁 checklists/
│   ├── vibe-coding-security.md     # Security audit prompts
│   └── saas-prelaunch.md          # Pre-launch checklist
│
├── 📁 guides/
│   ├── ai-website-seo-guide.pdf    # Full SEO guide by @aaditya.web
│   └── codvyn-workflow-guide.pdf   # Codvyn UI workflow guide
│
└── README.md

```
## 📚 Original Sources

Everything in this repo is built on top of these — go read them too:

| Resource | What it is | Link |
|---|---|---|
| Codvyn Workflow | Full visual-first UI dev workflow | [codvyn.in](https://codvyn.in) |
| Architecture Diagram Generator | Skill + template by Cocoon AI | [GitHub →](https://github.com/Cocoon-AI/architecture-diagram-generator) |
| AI Website SEO Guide | Hindi SEO guide for vibecoders | by [@aaditya.web](https://instagram.com/aaditya.web) |
| Vibe Coding Security Checklist | Security prompts for fast devs | included in repo |

<br/>

---

## 🤝 Contributing

This is a living document — the vibe coding ecosystem changes fast.

If you've found a better prompt, a missing checklist item, a broken tool,
or a workflow that works better than what's here — PRs are open.

**Ways to contribute:**
- Found a bug or outdated info → [Open an issue](../../issues)
- Have a better prompt → Edit the relevant Phase section + PR
- Found a tool that fits the workflow → Add it with context of *where* it fits
- Translated to another language → Add it under `/translations`

**One rule:** Every addition must be something you've actually used.
No theoretical tools, no untested prompts.

---

<div align="center">

## Credits

Built on the shoulders of people who actually ship things.

[![Codvyn](https://img.shields.io/badge/Codvyn%20Workflow-codvyn.in-0ea5e9?style=for-the-badge)](https://codvyn.in)
[![Cocoon AI](https://img.shields.io/badge/Architecture%20Diagrams-Cocoon%20AI-a78bfa?style=for-the-badge)]([mailto:hello@cocoon-ai.com](https://github.com/Cocoon-AI/architecture-diagram-generator))
[![aaditya.web](https://img.shields.io/badge/SEO%20Guide-@aaditya.web-e1306c?style=for-the-badge&logo=instagram)](https://instagram.com/aaditya.web)
[![saban.talks](https://img.shields.io/badge/Pre--Launch%20Checklist-@saban.talks-e1306c?style=for-the-badge&logo=instagram)](https://www.instagram.com/saban.talks)

<br/>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f172a,50:1e3a5f,100:0ea5e9&height=120&section=footer&fontSize=16&fontColor=94a3b8&text=Ship%20fast.%20Ship%20right.%20%E2%AD%90%20Star%20the%20repo%20if%20this%20helped.&fontAlignY=65" width="100%"/>

</div>

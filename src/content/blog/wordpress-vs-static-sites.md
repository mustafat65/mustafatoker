---
title: "Do You Still Need WordPress? Static Sites Are Winning the Argument"
description: "Yoast SEO's founder moved his blog to Astro. The WordPress community pushed back hard. Here's what both sides get right — and where each approach actually makes sense."
date: 2026-03-22
tags: ["wordpress", "static sites", "astro", "web development", "cms"]
---

The man who built Yoast SEO — the plugin that helped millions of WordPress sites rank on Google — just moved his own blog off WordPress.

Joost de Valk rebuilt joost.blog on [Astro](https://astro.build/), deployed it on Cloudflare Pages, and wrote a post explaining why. His argument: most websites don't need a CMS. People want a website. They never actually wanted the admin panel.

The WordPress community did not take this quietly.

## What Joost Actually Said

De Valk's post, ["Do you need a CMS?"](https://joost.blog/do-you-need-a-cms/), published March 21, 2026, makes a focused argument. He ran WordPress for years. He built the most popular SEO plugin in its ecosystem. And when he relaunched his personal site, he chose Markdown files, a static build tool, and a global CDN.

No database. No PHP. No plugin updates.

He still gets full-text search, comments, structured data, RSS feeds, and auto-generated Open Graph images. What he dropped was everything underneath that didn't add value for his use case.

His SEO take is the part that stings for the WordPress ecosystem: everything Yoast SEO does — sitemaps, meta tags, canonical URLs, JSON-LD schema — can be done in a static site generator. Often cleaner, because there's no plugin conflict touching your HTML head.

He's also direct about where WordPress still belongs: multi-user editorial teams, e-commerce, membership sites, LMS platforms. He's building his own community project, Rondo, on WordPress for exactly those reasons.

## The Community Response

WordPress developers pushed back fast.

Cameron Jones, a longtime WordPress developer, pointed out what many practitioners feel: the editing experience argument isn't solved yet. Clients can't push commits to a Git repository. Non-technical users aren't opening terminal windows to publish a blog post.

Dipak Gajjar and others raised the plugin ecosystem point. WordPress has 60,000+ plugins. WooCommerce alone powers a massive share of global e-commerce. That ecosystem doesn't exist for static sites.

Kent Langley framed it differently: static sites are a developer preference, not a universal solution. The web Almanac shows 67% growth in static and hybrid architectures among top sites — but that's among sites built by people who track the Web Almanac.

Onur and others noted that the "AI will replace the admin panel" argument, while directionally true, is optimistic about timing. We're not there yet for most clients.

Vinny Green added a perspective worth taking seriously: the cost argument cuts both ways. Static hosting is cheap, but the developer time to set up CI/CD pipelines, handle image optimization, and manage deployments adds up. For a simple brochure site, WordPress with a quality host might genuinely be faster to ship.

## The Actual Comparison

Here's how the two approaches stack up across the areas that matter most:

### Performance

Static sites win on raw speed. HTML files served from a CDN edge have almost nothing to do when a request arrives. WordPress running PHP and hitting a database on every request is inherently slower at baseline.

That said, a well-configured WordPress setup — good caching plugin, Cloudflare in front, optimized theme — closes most of the gap in practice. Core Web Vitals are passable on both. TTFB on static can hit 10–50ms. WordPress with caching typically lands at 50–300ms.

### Security

Static sites have a dramatically smaller attack surface. There's no database to inject, no PHP interpreter to exploit, no admin panel to brute-force. The main security work is keeping your build dependencies updated.

WordPress security is primarily a plugin problem. Core WordPress has been stable for years. But plugins are part of WordPress — you don't get to exclude them from the security conversation. A site with 20 plugins has 20 potential attack surfaces.

### SEO

WordPress wins on tooling. Rank Math, Yoast SEO, and similar plugins handle technical SEO with a UI. Sitemaps, redirects, schema markup, breadcrumbs — all configurable without touching code.

Joost's counterargument is valid but has a catch: yes, you can do all of that in a static site. But you or a developer has to build it. The question is whether your time is better spent there or on content.

### Content Management

This is where WordPress remains clearly ahead for most real-world scenarios.

A client who needs to publish three blog posts a week, update product descriptions, and manage an events calendar isn't switching to Markdown and Git. WordPress's admin panel, for all its complexity, solves a genuine human problem: making the web editable for people who aren't developers.

The AI argument — that chatbots will replace the admin panel — is real. De Valk is right that the direction is there. But "direction" and "ready for client handoff" are different things.

### Cost

Static sites are nearly free to host. Cloudflare Pages, Vercel, and Netlify all offer generous free tiers. For a personal blog or small business site with no special requirements, you can pay essentially nothing beyond the domain.

WordPress costs more when you add it up honestly: shared hosting runs $5–15/month, but quality managed hosting starts at $30+. Add Rank Math Pro, a premium theme, backup plugin, and a security plugin and you're looking at $300–600/year before any development work.

For a simple site, that's real money. For a complex application, it's table stakes.

### AI Workflow Compatibility

This one is interesting and genuinely new.

AI tools like Claude Code work more naturally with static sites. Clean HTML files, no abstraction layers, direct file access — an AI coding assistant can make changes, commit them, and deploy in a single workflow. The feedback loop is tight.

WordPress AI integration exists and is powerful (REST API, WP-CLI, Application Passwords), but it involves more moving parts. Plugins, database queries, theme templates — there's more for an AI to understand and more that can break.

For developer-owned sites where AI is part of the workflow, static sites have a real and growing advantage.

## The Interactive Comparison

<comparison-table />

*(The full comparison table with tabs for Performance, Security, SEO, Content Management, Cost, and AI compatibility is embedded above.)*

## Who Should Use What

**WordPress makes sense when:**
- Non-technical people need to manage content independently
- You need WooCommerce or another established e-commerce solution
- Multiple editors need roles, scheduling, and approval workflows
- You're building an application, not just a site
- Your client expects a CMS and isn't open to alternatives

**Static sites make sense when:**
- You or a developer will manage the site
- Performance and security are top priorities
- The content is relatively stable (portfolio, documentation, personal blog)
- You want near-zero hosting costs and maintenance
- AI tools are part of your publishing workflow

**The honest answer:** De Valk is right that most websites are simpler than the tools we use to build them. A five-page business site with a blog doesn't need a database. But most of those sites have non-technical owners who need to make updates — and that's where WordPress still earns its place.

The prediction that AI removes the CMS's core advantage is probably correct. It's just a question of when "probably correct" becomes "reliably works in production for real clients."

## FAQs

**Is WordPress dying?**

No. WordPress powers around 43% of the web and that number has only recently started declining slightly. It's not dying — but it's also not growing the way it was five years ago. The shift is real, but gradual.

**Can I do SEO on a static site?**

Yes. Everything a WordPress SEO plugin does is HTML output. Any modern static site generator can produce that same HTML. The difference is tooling — WordPress gives you a UI, static sites require configuration. For developers, that's not a problem. For everyone else, it adds friction.

**What is Astro and why did Joost use it?**

[Astro](https://astro.build/) is a modern static site framework that builds fast, content-focused websites. It ships minimal JavaScript by default, works with Markdown files, and integrates with Cloudflare Pages for global deployment. De Valk chose it for performance, simplicity, and the ability to add interactive components where needed.

**What does "static site" actually mean?**

A static site is pre-built HTML files. When someone visits a page, the server sends a file that already exists — there's no database query, no code execution. The content is "baked in" at build time. Updating a static site means changing a file, rebuilding, and redeploying. With modern tools like Cloudflare Pages, that process takes about 30 seconds after a Git push.

**Will AI replace WordPress admin panels?**

The direction is clear. If you can tell an AI "publish a post about our spring hours" and it edits a file, commits, and deploys — the visual admin panel becomes optional. De Valk thinks this transition is closer than most people expect. Skeptics think non-technical clients need more than a chat interface. Both have a point.

---

*Sources: [Joost de Valk — Do you need a CMS?](https://joost.blog/do-you-need-a-cms/) · [Cameron Jones on WordPress development](https://x.com/cameronjonesweb/status/2035379570124394918) · [Dipak Gajjar on the plugin ecosystem](https://x.com/dipakcgajjar/status/2034101134684787159) · [Onur on real-world editing](https://x.com/onuro/status/2035616466565820522) · [Kent Langley on developer preference vs. universal solution](https://x.com/KentLangley/status/2035780423171866626) · [Vinny Green on actual cost of static](https://x.com/vinnysgreen/status/2035720532432466041) · [Joost de Valk on X](https://x.com/jdevalk/status/2035326856103121278)*

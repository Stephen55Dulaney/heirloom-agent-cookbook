# Recipe: The Health Inspection (SEO Audit)

> Before you rearrange the stall, find out what's quietly spoiling in the back. Most of what hurts your
> ranking is invisible from the front — this recipe walks the whole kitchen with a clipboard.

## What you're cooking

Your site isn't showing up in search the way it should, and you can't see why. The pages look fine to
you. But search engines see a different site than your visitors do — one made of crawl paths, tags,
load times, and signals of trust — and something in there is holding you back. Guessing which thing is
how weeks disappear.

This recipe runs a structured inspection: it checks whether search engines can even find and index your
pages, whether the site is fast and sound, whether each page's on-page details are in order, whether the
content deserves to rank, and whether the site reads as trustworthy. What you get back is a prioritized
report — the top problems first, each with what's wrong, how bad it is, the evidence, and the specific
fix — not a vague "improve your SEO."

You don't need to know what any of these terms mean yet. Paste this card into your AI (Claude Code,
Codex, or similar), tell it your site and what you sell, and it does the walkthrough and explains each
finding in plain language.

## Before you start

Read **The Mother Stock** first (`recipes/marketing/product-marketing-context.md`) if it exists — it
holds your positioning, your audience, and the keywords that matter, so the AI shouldn't re-ask what's
already written down. Only gather what it doesn't cover:

- **Site context.** What kind of site is this (a software product, a store, a blog, a local business)?
  What is the main business goal for search, and which topics or search terms matter most?
- **Current state.** Any known problems? Roughly how much organic traffic do you get now? Any recent
  redesign or move to a new address (a "migration")?
- **Scope and access.** The whole site or specific pages? Do you have access to Google Search Console —
  Google's free report on how your site performs in search? Who are your top competitors in search?

## The method

Inspect in priority order, because a fix low on the list is wasted if a problem high on the list is
blocking it. **First, crawlability and indexation** — can search engines find your pages and add them to
their index at all? **Then technical foundations** — is the site fast and functional? **Then on-page
optimization** — are the page details in order? **Then content quality** — does the page deserve to
rank? **Last, authority** — does the site read as credible?

**Crawlability and indexation.** Check the robots file for accidental blocks on important pages, and that
it points to a sitemap. Check that the XML sitemap exists, is submitted to Search Console, and lists only
the canonical, indexable pages. Confirm important pages sit within three clicks of the homepage and
nothing is orphaned (a page with no internal links pointing to it). Watch for the classic index-killers:
a stray "noindex" tag on a page you want ranked, canonical tags pointing the wrong way, redirect chains
or loops, soft 404s, and duplicate pages with no canonical to settle which is the original. Confirm the
site is consistent about www-versus-not and trailing slashes, and that everything resolves to HTTPS.

**Technical foundations.** Measure the Core Web Vitals — Google's three speed-and-stability numbers —
against their thresholds: Largest Contentful Paint (how fast the main content appears) under 2.5 seconds,
Interaction to Next Paint (how fast the page reacts to a click) under 200 milliseconds, and Cumulative
Layout Shift (how much the page jumps around while loading) under 0.1. Check server response time, image
sizes, and caching. Confirm the site is genuinely mobile-friendly — responsive, tappable, no horizontal
scroll, same content as desktop — since Google judges the mobile version first. Confirm valid HTTPS with
no mixed content, and clean, readable URLs.

**On-page optimization.** Titles: unique per page, primary keyword near the front, 50 to 60 characters
so they don't get cut off in results, and brand name at the end. Meta descriptions: unique, 150 to 160
characters, with a real reason to click — never auto-generated filler. Headings: exactly one H1 per page
carrying the primary keyword, and a clean H1-to-H2-to-H3 hierarchy with no skipped levels. Content: the
keyword in the first 100 words, related terms used naturally, and enough depth to actually answer the
searcher. Images: descriptive filenames and real alt text, compressed and modern formats. Internal
links: important pages well linked with descriptive anchor text, no broken links. And check for
cannibalization — two of your own pages fighting over the same keyword and splitting the vote.

**Content quality and authority.** Judge the page against E-E-A-T — Experience, Expertise,
Authoritativeness, Trustworthiness: first-hand experience and original data, visible author credentials,
recognition in the field, and the trust basics (accurate claims, contact info, a privacy policy, HTTPS).
Ask whether the page is genuinely more complete than what currently ranks above it.

**One critical caution on schema.** Schema markup (structured data — see The Labeled Jars) often cannot
be detected by simply fetching a page's raw HTML, because many tools inject it with JavaScript that a
plain fetch never runs. Never report "no schema found" from a raw fetch alone. Verify with a rendering
tool — a real browser, or Google's Rich Results Test — before making any claim about schema.

Deliver the report with an executive summary (overall health plus the top three to five priorities), then
findings grouped by area, each with the issue, its impact rated high/medium/low, the evidence, and the
fix — ending in an action plan ordered as: critical blockers, high-impact improvements, quick wins,
then long-term work.

## Acceptance Criteria (how you know it worked)

- [ ] The report leads with an executive summary naming the top three to five priority issues.
- [ ] Every finding states the issue, its impact rating, the evidence it was found by, and a specific fix.
- [ ] Findings are checked in priority order, and crawl/indexation blockers appear before cosmetic fixes.
- [ ] Any claim about schema markup is backed by a rendering tool, never by a raw HTML fetch alone.
- [ ] Title-tag, meta-description, heading, and Core Web Vitals checks cite the actual thresholds, not
  vague advice.
- [ ] The report ends with an action plan ordered from critical blockers to long-term work.

## Primary metric

Organic search traffic — the number of visitors arriving from unpaid search results, measured before the
fixes and again after, against the baseline you recorded at the start.

## The bright lines (never cross)

- **Never report "no schema found" from a raw HTML fetch.** Confirm with a browser or the Rich Results
  Test first — false schema findings have shipped to real clients.
- **Never invent an audit finding you didn't verify.** Every issue needs evidence you can point to.
- **Never recommend a fix that games search engines** — keyword stuffing, doorway pages, hidden text.
  The job is to earn the ranking, not fake it.
- **Never skip the priority order.** A perfectly optimized title on a page Google can't crawl helps no one.

---

*A good inspection isn't about writing up every speck — it's about finding the one spoiled thing in the
back that's souring the whole stall, and saying plainly how to fix it.*

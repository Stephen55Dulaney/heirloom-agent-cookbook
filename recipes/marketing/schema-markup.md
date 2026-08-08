# Recipe: The Labeled Jars (Schema Markup)

> A shelf of unlabeled jars all look alike to a stranger. Label each one — what's inside, how much, when
> it was put up — and suddenly anyone can find exactly what they need. That's all schema markup is.

## What you're cooking

Search engines read your page, but they're guessing at what it means. Is that number a price or a
rating? Is that a product, an article, or an event? Is that block of text a list of questions and
answers? When they have to guess, you miss out on the richer search results — star ratings, prices,
FAQs, breadcrumbs shown right in the results — that draw the eye and the click.

This recipe adds structured data: a small, standardized description attached to a page that tells search
engines exactly what's inside, in a vocabulary they already understand (schema.org). Done right, it makes
your page eligible for "rich results" — those enhanced listings — and helps engines represent your
content accurately. It works for a company homepage, a blog post, a product page, an FAQ, a tutorial,
a local business, or an event.

You don't need to touch any code. Paste this card into your AI (Claude Code, Codex, or similar), tell it
what kind of page you're marking up and what's on it, and it builds and validates the markup with you.

## Before you start

Read **The Mother Stock** first (`recipes/marketing/product-marketing-context.md`) if it exists — it
holds your company details, product facts, and positioning, so the AI shouldn't re-ask what's already
written down. Only gather what it doesn't cover:

- **Page type.** What kind of page is this, and what's the primary content on it? That decides which
  markup fits and which rich results are even possible.
- **Current state.** Is there any schema on the page already? Any errors in it? Are any rich results
  already showing for the page?
- **Goals.** Which rich results are you hoping to earn, and what's the business value of getting them?

## The method

Four principles govern everything. **Accuracy first** — the markup must describe what's actually on the
page; never label content that isn't there, and keep the labels updated when the content changes.
**Use JSON-LD** — the format Google recommends, a small block of structured description placed in the
page's head; it's easier to maintain than markup woven into the visible page. **Follow Google's
guidelines** — only use types Google actually supports, and never use markup to fake eligibility.
**Validate everything** — test before you ship, then watch Search Console and fix errors promptly.

**Choose the type that matches the page.** Each type is like a labeled jar with required contents. An
Organization entry (for a company homepage or about page) carries a name and a URL, and ideally a logo,
social profile links, and a contact point. A WebSite entry can enable a search box in results. An Article
or BlogPosting carries a headline, an image, a publish date, and an author — and ideally a modified date
and publisher. A Product entry carries a name, an image, and an offer (which itself holds a price and an
availability), plus optional brand, rating, and reviews. A SoftwareApplication entry (for a software
product) carries a name and an offer. An FAQPage carries a main-entity list of question-and-answer pairs.
A HowTo carries a name and its ordered steps. A BreadcrumbList carries an ordered list of the trail's
items, each with its position, name, and link. A LocalBusiness carries a name and an address. An Event
carries a name, a start date, and a location.

**Combining types.** When a page is several things at once — say a company homepage that's also the main
site and shows breadcrumbs — you don't stack separate blocks; you gather them into one structured group
(schema.org calls it an "@graph") so the entries live together cleanly.

**Get the values right.** The most common failures are missing a required property, or supplying an
invalid value: dates must follow the ISO 8601 standard (a fixed year-month-day-time format), URLs must be
fully spelled out, and enumerated values (like an availability status) must be exact matches to the terms
schema.org defines. The deepest failure is a mismatch between the markup and the visible page — a rating
in the markup that appears nowhere on the page is both against the rules and a fast way to lose
eligibility.

**Validate before shipping.** Run the markup through Google's Rich Results Test and the schema.org
validator; confirm zero errors and no warnings, that every required property is present, and that the
markup matches the page's visible content. After launch, watch Search Console's enhancement reports for
errors that surface later. And a note that ties back to The Health Inspection: because JSON-LD is often
injected by JavaScript, a plain fetch of the raw HTML may miss it entirely — always verify with a
rendering tool, never conclude "no schema" from a raw fetch.

Deliver the finished markup ready to place, plus a short testing checklist confirming it validates, has
no errors or warnings, matches the page, and includes every required property.

## Acceptance Criteria (how you know it worked)

- [ ] The schema type matches the page's actual content and primary purpose.
- [ ] Every required property for that type is present, with valid values (ISO 8601 dates, fully
  qualified URLs, exact enumerations).
- [ ] The markup passes Google's Rich Results Test and the schema.org validator with zero errors and no
  warnings.
- [ ] Every value in the markup corresponds to something actually visible on the page.
- [ ] Where a page is several things at once, the types are combined into one clean group rather than
  scattered.
- [ ] A testing checklist is delivered alongside the markup, and validation is confirmed by a rendering
  tool, not a raw fetch.

## Primary metric

Rich results earned — the number of pages that show enhanced listings (ratings, prices, FAQs,
breadcrumbs) in search, confirmed valid in Search Console's enhancement reports.

## The bright lines (never cross)

- **Never mark up content that isn't on the page.** A label must match what's in the jar — invented
  ratings or prices are against Google's rules and cost you eligibility.
- **Never use a schema type Google doesn't support, or use markup to fake eligibility.** That's spam, and
  it gets penalized.
- **Never ship markup you haven't validated.** Test it, confirm zero errors, then deploy.
- **Never conclude "no schema" from a raw HTML fetch.** JavaScript-injected markup is invisible there —
  verify with a rendering tool.

---

*The jars were always full. All that was missing was the label — the plain little note that lets a
stranger reach straight for the right one instead of opening every lid to guess.*

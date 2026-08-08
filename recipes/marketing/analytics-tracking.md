# Recipe: The Day's Tally (Analytics Tracking)

> At close of market, the honest stallholder counts what actually sold — not what they hoped would. The
> tally is only worth keeping if you'll act on it tomorrow.

## What you're cooking

You have a website or an app and only a fog where the facts should be. How many people signed up? Where did
the ones who bought come from? Which step of the funnel loses people? Without measurement you're guessing, and
guessing is how good money follows bad.

This recipe turns an AI into an analytics expert and has it build you a **tracking plan** — the plain-language
list of exactly what gets recorded, when, and why. It covers the common tools (GA4, which is Google Analytics
4, plus Google Tag Manager and their kin), a consistent naming scheme so the data stays readable, the events
worth capturing, and the privacy guardrails that keep you on the right side of the law and of decency.

You don't need to be technical. Paste this card into Claude Code or Codex, tell it what you want to know and
what decisions the data will inform, and it will produce a tracking plan you can hand to a developer — or have
the AI implement — with every event named, described, and justified.

## Before you start

Tell the AI to read **The Mother Stock** first — `recipes/marketing/product-marketing-context.md`, the master
positioning document — if it exists, so it already knows your product and audience and only asks for the rest.

Then it needs the **business context** (what decisions this data will inform and what your key conversions
are), the **current state** (what's already tracked and which tools you use), and the **technical context**
(your tech stack, who will implement — developer or marketer — and any privacy or consent requirements). The
first question is the important one: if an event won't change a decision, it doesn't belong in the plan.

## The method

**Track for decisions, not for data.** Every event you capture should answer a question you'd actually act on.
Start from the questions — "what do I need to know, and what will I do about it?" — and work backwards to the
events. Vanity metrics that never change a decision are clutter; clean, sparse data beats a mountain of noise.

**Name everything consistently, and settle the scheme before you implement.** The recommended pattern is
object-then-action, all lowercase with underscores: `signup_completed`, `form_submitted`, `checkout_payment_completed`.
Be specific — `cta_hero_clicked` tells you more than `button_clicked`. Keep the *context* out of the event
name and put it in properties instead. Once a naming pattern is chosen, hold to it; renaming events after the
fact orphans your history.

**Build the plan as a table, not a guess.** Each row is one event with these columns: event name, category,
its properties, the trigger that fires it, and a note. Events fall into a few types — pageviews (mostly
automatic), user actions (clicks, form submits, feature use), system events (signup completed, purchase,
subscription changed), and custom conversions (goal completions, funnel stages). A lean marketing-site plan
usually needs only a handful: a call-to-action click (with the button text and location), a form submission
(with form type), a completed signup (with method and source), and a demo request. A product plan adds
onboarding-step-completed, feature-used, purchase-completed (with plan and value), and cancellation (with
reason).

**Attach properties, carefully.** Standard property groups: page (title, location, referrer), user (an
anonymous user id, user type, account id, plan type), campaign (source, medium, campaign, content, term), and
product (id, name, category, price). Use consistent property names, include only relevant context, don't
duplicate what the tool captures automatically — and never put personally identifiable information (a name,
an email, a raw address) into a property.

**Set up the tools in order.** For GA4: create the property and data stream, install the tag (directly or via
Google Tag Manager), turn on enhanced measurement, configure your custom events, then mark the important ones
as conversions in the admin. Google Tag Manager works in three parts worth understanding: tags (the code that
runs, like GA4 or an ad pixel), triggers (when a tag fires — a page view, a click), and variables (the dynamic
values, like clicked text). Events reach it through a "data layer," a tidy handoff of information from the page
to your tools.

**Keep your campaign links tagged.** UTM parameters are the labels on inbound links that tell analytics where
a visitor came from: source (google, newsletter), medium (cpc, email, social), campaign (spring_sale), content
(to tell two versions apart), and term (paid keywords). Lowercase everything, pick underscores or hyphens and
stick with it, be specific but short (`blog_footer_cta`, never `cta1`), and keep every UTM you use in one
spreadsheet so the same campaign never gets logged three different ways.

**Validate before you trust it.** Watch events fire in real time (GA4's DebugView, Tag Manager's preview mode,
a browser tag-assistant extension) and walk a checklist: events fire on the right triggers, property values
populate correctly, no duplicate events, it works across browsers and on mobile, conversions record, and — the
one people forget — no personal information is leaking through. When something's off, the usual suspects are a
misconfigured trigger (events not firing), a wrong data-layer path (wrong values), or two containers or a
double-firing trigger (duplicate events).

**Respect privacy as infrastructure, not an afterthought.** Cookie consent is required in the EU, UK, and much
of Canada; honor it with consent mode so tracking waits for permission. Anonymize IP addresses, collect only
what you need, keep no personal data in analytics properties, and make sure you can honor a user's deletion
request. This isn't only compliance — it's the difference between a tally you're proud of and one you'd hide.

## Acceptance Criteria (how you know it worked)

- [ ] A written tracking plan exists as a table: each event with name, description, properties, and trigger.
- [ ] Every event names a decision it will inform — nothing tracked "just in case."
- [ ] Event names follow one object-action, lowercase-underscore convention with no exceptions.
- [ ] Key events are marked as conversions, and each is verified firing in a live debug view.
- [ ] A validation pass confirms no duplicate events and no personal information in any property.
- [ ] Consent handling is in place for regions that require it, with a documented UTM naming convention.

## Primary metric

Percentage of key conversion events that fire correctly and completely — verified live in a debug view, with
their properties populated and no duplicates. A tally you can't trust is worse than no tally at all.

## The bright lines (never cross)

- **Never put personally identifiable information in analytics.** No names, emails, or raw addresses in event
  properties — use an anonymous id and keep the real identity out of the tally.
- **Never track without consent where it's required.** Wait for permission via consent mode; don't collect
  first and apologize later.
- **Never track an event you won't act on.** If it changes no decision, it's noise that hides the signal.
- **Never rename events casually.** A changed name breaks the history; settle the convention up front.
- **Never trust an implementation you haven't watched fire.** Verify live before you make a single call on it.

---

*The point of counting isn't the count — it's the better decision you make tomorrow because of it. Tally only
what you'll act on, keep the personal details out of the ledger, and check the numbers are real before you
trust them.*

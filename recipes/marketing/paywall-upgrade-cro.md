# Recipe: The Velvet Rope (Paywall & Upgrade CRO)

> A velvet rope isn't a wall. It's an invitation to the better room —
> extended at the moment someone can already feel the party on the other side.

## What you're cooking

You have free users who could be paying users, or paid users who'd get more from a higher tier. The upgrade prompt is where that happens — the paywall, the "you've hit your limit" screen, the trial-ending notice, the feature that's locked. Done badly, it's a wall that arrives before anyone cares and breeds resentment. Done well, it's a door that opens exactly when someone's ready to walk through.

This recipe turns an AI into an expert on in-app paywalls and upgrade flows. Its job is to convert free to paid — or lift a user to a higher tier — at the moment they've felt enough value to justify the commitment. It designs the paywall screen, picks the trigger, times the ask, and builds the upgrade path, or audits what you have. Paste this card in, describe your free-vs-paid model and where prompts fire today, and let it hang the rope in the right place.

This is the *in-product* upgrade moment — the user has already experienced value. For a public pricing page, see The Storefront (`recipes/marketing/page-cro.md`); for reaching the aha moment first, The First Bite (`recipes/marketing/onboarding-cro.md`).

## Before you start

Have the AI read **The Mother Stock** first — `recipes/marketing/product-marketing-context.md` — if it exists, and use it before asking you anything.

Then it needs: the upgrade context (freemium to paid, trial to paid, tier upgrade, feature upsell, usage limit), the product model (what's free, what's gated, what triggers prompts, current conversion rate), the pricing model (per seat, usage-based, or flat), the user journey (when this appears and what they were trying to do), and — crucially — your "aha moment," because value comes before the ask.

## The method

Four principles govern the whole thing. **Value before ask** — the user should have experienced real value first; the upgrade should feel like the natural next step, timed *after* the aha moment, never before. **Show, don't just tell** — demonstrate the paid feature, preview what they're missing, make it tangible. **Friction-free path** — when they're ready, upgrading is easy and pricing isn't a scavenger hunt. **Respect the no** — never trap or pressure; make continuing free easy, and keep the trust intact for a later conversion.

**Pick the trigger point.** A *feature gate* fires when the user clicks a paid-only feature — explain why it's paid, show what it does, offer a quick unlock and an option to continue without. A *usage limit* fires when they hit a cap — show it clearly, show what upgrading grants, and don't cut them off abruptly. *Trial expiration* deserves early warnings (7, 3, 1 day), a clear statement of what happens when it ends, and a summary of the value they've received. *Time-based* prompts, after some days of free use, gently remind and highlight unused paid features — easy to dismiss.

**Build the screen from these parts:** a headline about what they *get* ("Unlock [feature] to [benefit]"), a value demonstration (a preview, a before/after, "with Pro you could…"), a focused feature comparison with the current plan marked, clear and simple pricing with monthly-vs-annual options, social proof (a customer quote, "X teams use this"), a specific value-oriented CTA ("Start getting [benefit]"), and — always — a clear escape hatch ("Not now," "Continue with Free").

The shapes differ by trigger. A *feature-lock* screen leads with the locked feature, previews it, lists what it unlocks, and pairs the upgrade button with a "maybe later." A *usage-limit* screen shows the meter at 100%, states the free-vs-paid limits plainly, and offers both upgrade and a way to stay free (delete something to make room). A *trial-expiration* screen names what they'll lose *and* what they've accomplished, then offers to continue paid, remind later, or downgrade.

**Time it with care.** Show it after a value moment and before frustration, after activation, or when they hit a genuine limit. Do *not* show it during onboarding (too early), mid-flow when they're concentrating, or repeatedly after a dismissal. Frequency: limit per session, cool down for *days* not hours after a dismiss, and watch for annoyance signals.

**Smooth the path from yes to paid:** minimize steps, keep it in-context where you can, pre-fill what you know. After they upgrade: immediate access to the features, a confirmation and receipt, and a short guide to what they just unlocked.

Deliver the paywall design (type, trigger, timing, components, copy) plus the test plan — trigger timing, headline and copy, price presentation, trial length, feature emphasis, layout — measured on impression rate, click-through to upgrade, completion, revenue per user, and post-upgrade churn.

## Acceptance Criteria (how you know it worked)

- [ ] The prompt fires only after the user has hit the aha moment or a genuine limit — never during onboarding or mid-flow.
- [ ] Every paywall screen has a clearly visible escape hatch ("Not now" / "Continue with Free").
- [ ] The screen shows or previews the paid value rather than only describing it.
- [ ] Pricing and plan differences are clear and simple, with the current plan marked.
- [ ] After a dismissal there's a cool-down measured in days, and prompts are capped per session.
- [ ] The upgrade path is minimal-step and grants access immediately on completion.

## Primary metric

Free-to-paid conversion rate — the share of eligible users who upgrade from the prompt. Keep an eye on post-upgrade churn beside it, so you're converting people who stay, not people who bounce.

## The bright lines (never cross)

- **No dark patterns.** Never hide the close button, never confuse the plan selection, never use guilt-trip copy.
- **Never ask before value is delivered.** Prompting before the aha moment kills the conversion and the trust.
- **Never block a critical flow.** Don't wall off something the user genuinely needs to do just to force the upgrade.
- **Respect the no, and keep it easy to stay free.** A pressured yes today is a churn and a bad review tomorrow.

---

*A velvet rope works because the room beyond it is real and the guest can already hear it. Extend the invitation at the moment they lean toward the door, make the better room easy to enter, and make "not yet" just as graceful — the ones who wave you off today are the ones who upgrade next month.*

# Recipe: The Tap on the Shoulder (Popup CRO)

> A good tap on the shoulder is a favor: the right offer, at the moment it helps.
> A bad one is a stranger blocking the door. The whole craft is telling them apart.

## What you're cooking

Popups have a deserved bad reputation — because most of them fire too soon, offer too little, and are too hard to close. But a well-timed, genuinely useful offer, appearing exactly when someone is engaged or about to leave, is one of the highest-converting tools you have.

This recipe turns an AI into a popup and modal expert whose goal is to convert *without* annoying people or cheapening the brand. It designs the popup — type, trigger, targeting, frequency, and copy — or audits one that isn't working. Paste this card in, tell it what the popup is for, and let it build the tap on the shoulder that helps rather than intrudes.

For the form inside the popup, see The Order Slip (`recipes/marketing/form-cro.md`); for the page around it, The Storefront (`recipes/marketing/page-cro.md`).

## Before you start

Have the AI read **The Mother Stock** first — `recipes/marketing/product-marketing-context.md` — if it exists, and use it before asking you anything.

Then it needs: the popup's purpose (email capture, lead magnet, discount, announcement, exit-intent save, feature promo, survey), how any current popup performs and what triggers it, whether you've had user complaints, and the traffic context — sources, new vs. returning visitors, and which pages it shows on. The mobile-vs-desktop split matters, because mobile can't detect exit intent.

## The method

Three principles decide whether a popup helps or harms. **Timing is everything** — too early is an interruption, too late is a missed chance, right-on-time is a helpful offer at the moment of need. **Value must be obvious** — a clear, immediate benefit, relevant to the page, worth the interruption. **Respect the user** — easy to dismiss, never trapping or tricking, remembering their choice.

**Choose the trigger to match intent.** Time-based: don't fire at 5 seconds; 30–60 seconds signals real engagement. Scroll-based: 25–50% depth, good for long content ("you're halfway through — get more like this"). Exit intent: the cursor heads for the close button — a last-chance capture, great for e-commerce and lead gen; on mobile, substitute the back button or a scroll-up. Click-triggered: the user opens it themselves — zero annoyance, ideal for lead magnets and gated content. Page-count: after several pages, signalling research behavior. Behavior-based: cart abandonment, pricing-page visits, repeat visits — your highest-intent moments.

**Match the type to the goal.** An *email-capture* popup needs a real value prop (not just "Subscribe"), a single email field, and maybe an incentive. A *lead magnet* shows what they get (a cover image, a preview), promises something specific, keeps to minimal fields, and sets an instant-delivery expectation. A *discount* states the offer plainly (10%, $20, free shipping), can carry a deadline, and is one-use per visitor. An *exit-intent* popup acknowledges the leaving, makes a *different* offer than the entry one, and answers a common objection. An *announcement banner* sits at the top, carries one message, is dismissable, and doesn't live forever. A *slide-in* enters from a corner without blocking content — the gentlest form.

**Design in a clear hierarchy:** headline first (largest), then the offer, then the form or CTA, then an easy close. Size it 400–600px on desktop — never the whole screen — and on mobile use a full-width bottom or centered card, never a full-screen takeover before content. The close button is always visible (top-right by convention), big enough to tap, with a "No thanks" text link and click-outside-to-close as alternatives.

**Write copy that earns the interruption.** Headlines can be benefit-driven, a question, a command, social proof, or curiosity. Subheads expand the promise and remove an objection ("No spam, ever"). CTA buttons use first person and name the value ("Get My Discount," "Send Me the Guide" — not "Submit"). Decline options stay polite and never guilt-trip: "No thanks" or "Maybe later," never "No, I don't want to save money."

**Set frequency rules and honor them.** Show at most once per session, remember dismissals, and wait 7–30 days before showing again. Target thoughtfully — new vs. returning, by source, by page type — and exclude anyone who already converted or recently dismissed. Exclude checkout and conversion flows entirely.

**Stay compliant and accessible.** Clear consent language, a privacy-policy link, no pre-checked opt-ins. Keyboard-navigable (Tab, Enter, Esc), a focus trap while open, screen-reader compatible, sufficient contrast, never relying on color alone. And mind Google's guidance: intrusive interstitials — especially full-screen on mobile before content — hurt SEO.

Deliver the design (type, trigger, targeting, frequency, full copy, mobile notes) and, if several popups run together, the conflict rules that keep them from stacking. Useful benchmarks: email popups convert around 2–5%, exit-intent around 3–10%, and click-triggered higher (10%+, since people opt in).

## Acceptance Criteria (how you know it worked)

- [ ] The trigger matches visitor intent (engaged time, scroll, exit, or self-initiated click) — never a 5-second interrupt.
- [ ] A close option is always visible, easy to tap, and Escape / click-outside both dismiss it.
- [ ] Frequency is capped (at most once per session; 7–30 days before repeating) and dismissals are remembered.
- [ ] Checkout and active conversion flows are excluded from popup targeting.
- [ ] Decline copy is polite and never uses guilt or shame.
- [ ] The popup is keyboard-navigable with a focus trap, and never a full-screen takeover before content on mobile.

## Primary metric

Popup conversion rate — of the people who see it, the share who take the offer. Read it alongside the immediate close rate, which tells you whether the tap on the shoulder felt like a favor or an intrusion.

## The bright lines (never cross)

- **Never trap or trick.** The close must be obvious and one tap away; no hidden X, no fake-out buttons.
- **No guilt-trip declines.** "No, I don't want to save money" is a dark pattern — refuse it every time.
- **Honor the user's no.** Remember dismissals and respect the cool-down; don't re-nag someone who already said not now.
- **Never interrupt a conversion in progress.** Keep popups out of checkout and active signup flows.

---

*The difference between a helpful nudge and an ambush is timing, honesty, and an easy exit. Tap the shoulder only when you've something worth offering, make the "no thanks" as easy as the "yes," and you'll be the stall people are glad stopped them.*

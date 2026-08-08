# Recipe: The Price Ladder (Pricing Strategy)

> Set the rungs so the climb feels natural — good, better, best — each step worth more than the last,
> priced for the value on the plate, not the cost of the ingredients.

## What you're cooking

Pricing is the most nervous decision most founders make, so they copy a competitor or pick a round number
and hope. **This recipe designs your pricing deliberately: the tiers, what goes in each, what you charge
*for*, and the actual dollar amounts — a ladder where each rung climbs in value and the middle rung is the
one most people should choose.**

The pain it solves is money left on the table (or scared away): prices set by cost instead of value, tiers
that don't clearly differ, a value metric that doesn't grow as the customer grows. This recipe produces a
packaging-and-pricing plan grounded in willingness-to-pay research and the good-better-best framework, plus
guidance on when and how to raise prices later.

Paste this card into Claude Code or Codex and say "design my pricing." The AI acts as a SaaS pricing and
monetization expert.

## Before you start

**Read The Mother Stock first** (`recipes/marketing/product-marketing-context.md` — the master
positioning document). It holds your audience, your competitors, your differentiation, and your proof
points — the raw material of value-based pricing. Only ask for what it doesn't cover: your current pricing
if any, your go-to-market motion (self-serve, sales-led, or hybrid), current conversion rate, ARPU
(average revenue per user) and churn, any pricing feedback from customers, and whether you're optimizing
for growth, revenue, or profitability. If no Mother Stock exists, offer to build it first.

## The method

**Three axes to decide, in this order.** Packaging (what's included at each tier), the **pricing metric**
(what you charge for), and the price point (the actual amount). Most founders jump straight to the amount;
the metric and packaging matter more.

**Price to value, not to cost.** Your cost to serve is only a floor for sanity, never the basis. Think of
a band: the customer's perceived value is the ceiling, the next-best alternative is the floor for your
differentiation, and **your price sits between the next-best alternative and perceived value.** Cost tells
you if you can survive; value tells you what to charge.

**Choose a value metric that grows with the customer.** The metric is what you charge for, and a good one
aligns price with value delivered, is easy to understand, scales as the customer grows, and is hard to
game. Common ones: per user/seat (collaboration tools like Slack, Notion), per usage (variable
consumption, AWS, Twilio), per feature (modular products), per contact or record (CRM, email tools), per
transaction (payments, marketplaces), or a flat fee (simple products like Basecamp). The test: *"as a
customer uses more of this metric, do they get more value?"* If yes, it's a good metric; if no, your price
is disconnected from value.

**Build the ladder: good, better, best.** Three tiers is the industry standard — two is simple but leaves
money on the table, four or more risks decision paralysis.
- **Good (entry):** core features, limited usage, low accessible price — removes the barrier to entry.
- **Better (recommended):** full features, reasonable limits, your anchor price — where most customers
  should land.
- **Best (premium):** everything, advanced features, higher limits, often **2-3x the Better price** —
  captures your high-value customers.
Differentiate the rungs by feature gating (basic vs. advanced), usage limits (same features, more room),
support level (email → priority → dedicated), or access (API, SSO, custom branding). Highlight the
recommended tier so the eye lands there.

**Research willingness to pay instead of guessing.** The **Van Westendorp** method asks four questions —
at what price is it *too expensive* to consider, *too cheap* to trust, *expensive but worth considering*,
and *a bargain* — and the intersections reveal an acceptable price band. **MaxDiff** shows customers sets
of features and asks which matters most and least, which tells you what belongs in which tier.

**Freemium vs. free trial.** Freemium fits when the product has viral/network effects, free users create
value, and marginal cost to serve them is low — but free users may never convert and it can devalue the
product. A free trial fits when the product needs time to prove value, setup is involved, or price points
are higher; 7-14 days for simple products, 14-30 for complex, ideally with full access and clear countdown
reminders. Requiring a credit card upfront roughly doubles trial-to-paid conversion (about 40-50% vs.
15-25%) at the cost of lower trial volume.

**Enterprise / custom tier.** Add a "Contact Sales" option when deals exceed ~$10k ARR or customers need
custom contracts, security/compliance, or hands-on onboarding. Table stakes for it: SSO/SAML, audit logs,
admin controls, an uptime SLA, security certifications.

**When to raise prices.** The signals: competitors have raised theirs, prospects don't flinch, you hear
"it's so cheap," conversion is very high (>40%), churn is very low (<3% monthly), or you've added real
value since you last priced. Do it gracefully: grandfather existing customers, announce 3-6 months out,
tie the increase to new features, or restructure the plans entirely.

**On the pricing page:** a clear comparison table with the recommended tier highlighted, a monthly/annual
toggle, an annual discount (typically 17-20%), a CTA per tier, "who each tier is for," an FAQ, and trust
signals. Use anchoring (show the higher option first), the decoy effect (make the middle the best value),
and charm vs. round pricing ($49 signals value, $50 signals premium).

## Acceptance Criteria (how you know it worked)

- [ ] **A value metric is named** and passes the test — using more of it clearly delivers the customer more value.
- [ ] **Prices sit in the value band** — between the next-best alternative and perceived value, not derived from cost.
- [ ] **Tiers are genuinely differentiated** — a reader can say in one sentence why they'd move from Good to Better to Best.
- [ ] **The recommended (Better) tier is the anchor**, visibly highlighted, with Best roughly 2-3x its price.
- [ ] **Willingness-to-pay reasoning is shown** — Van Westendorp and/or MaxDiff informed the numbers, not a guess.
- [ ] **Freemium-vs-trial is decided with a reason** tied to this product's dynamics, not defaulted.

## Primary metric

`value-alignment` — does price rise in step with the value the customer receives as they climb the ladder?
When it does, growth and revenue take care of themselves; when it doesn't, no clever page fixes it.

## The bright lines (never cross)

- **Never fabricate competitor prices or willingness-to-pay data.** If a competitor's pricing is unknown,
  say so and flag it for real research — don't invent a number that anchors the whole ladder.
- **Never price from cost alone.** Cost is a floor, not the basis. Pricing to cost systematically leaves
  value uncaptured.
- **Never change a live customer's price without a graceful path.** Grandfather, announce well ahead, or
  tie it to added value — surprise increases burn trust and spike churn.
- **Don't over-tier.** More than three or four rungs usually causes decision paralysis, not more revenue.

---

*A good price ladder feels less like a wall and more like a staircase — each step an easy, obvious climb
toward more value. Build the rungs to fit the customer, and they'll walk up on their own.*

# Recipe: The Mother Stock (Product Marketing Context)

> Positioning is the stock every dish in this stall is built on — make it once, make it right,
> and every recipe after it tastes of the same product.

## What you're cooking

Every good kitchen keeps a pot of stock going. It's the base you reach for again and again, so you
never start a dish from cold water. **The Mother Stock is that pot for your marketing: a single
positioning document that says who your product is for, what problem it solves, who you're up against,
and how you talk about it.** Positioning — the deliberate choice of what your product *is* in the
customer's mind — is the one thing every other recipe in this stall needs before it can start.

The pain this fixes is repetition. Without it, you re-explain your product, your audience, and your
competitors to the AI every single time you write a landing page, a launch plan, or a pricing tier.
Worse, the answers drift — the AI guesses slightly differently each time, and your marketing stops
sounding like one product. This recipe produces one master file, **`recipes/marketing/product-marketing-context.md`**
in your own project, that every other marketing recipe reads first. Write it once; draw from it forever.

Paste this card into Claude Code or Codex and say "build my Mother Stock." The AI will interview you
(or draft a first version from your website and repo, then have you correct it) and save the document.

## Before you start

This is the one card that has no Mother Stock to read first — **you are making the stock.** So the AI's
job here is to conduct the interview, not to look something up.

Two ways to begin, and the AI should offer both:

- **Auto-draft from what exists (recommended, and faster).** The AI reads your README, landing page,
  marketing copy, about page, and any existing docs, then drafts a first version of every section. It
  presents the draft and asks the two questions that matter: *"What needs correcting? What's missing?"*
  You react to something concrete instead of staring at a blank page.
- **Start from scratch by interview.** The AI walks through the sections below one at a time —
  explaining what it's capturing, asking, confirming, moving on. It never dumps all the questions at once.

The rule that makes the stock rich instead of watery: **push for the customer's exact words.** A verbatim
phrase a real customer used ("I was drowning in spreadsheets") beats a polished description you invented.

## The method

The document captures twelve sections. Not every product needs all of them — a consumer product can
skip the B2B personas — but this is the full pantry:

1. **Product overview** — the one-liner, what it does in 2-3 sentences, the *category* (the "shelf" you
   sit on, i.e. how customers search for you), the product type, and the business model.
2. **Target audience** — the kind of company you sell to, the decision-makers, the primary use case, and
   the "jobs to be done": the 2-3 things customers actually hire your product to accomplish.
3. **Personas (B2B only)** — for each stakeholder in the buying decision (user, champion, decision maker,
   financial buyer, technical influencer): what they care about, their challenge, the value you promise them.
4. **Problems and pain points** — the core challenge before they found you, why current solutions fall
   short, what it costs them (time, money, missed chances), and the emotional tension (stress, fear, doubt).
5. **Competitive landscape** — split three ways: *direct* competitors (same solution, same problem),
   *secondary* (different solution, same problem), and *indirect* (a conflicting approach entirely). For
   each, how it falls short for the customer.
6. **Differentiation** — the capabilities alternatives lack, how you solve it differently, why that's
   better, and why customers ultimately choose you.
7. **Objections and anti-personas** — the top 3 objections heard in sales and how to answer each, plus a
   clear picture of who is *not* a good fit.
8. **Switching dynamics** — the four forces that move a customer: *push* (frustration with today), *pull*
   (what attracts them to you), *habit* (what keeps them stuck), and *anxiety* (what worries them about switching).
9. **Customer language** — how customers describe the problem and your solution, in their words; the
   phrases to use, the phrases to avoid, and a glossary of product-specific terms.
10. **Brand voice** — tone, communication style, and 3-5 adjectives for the brand's personality.
11. **Proof points** — metrics and results worth citing, notable customers, testimonial snippets, and the
    main value themes with the evidence behind each.
12. **Goals** — the primary business goal, the key conversion action you want people to take, and current
    metrics if known.

Save the finished document as **`recipes/marketing/product-marketing-context.md`** in the human's project.
Then tell them plainly: every other marketing recipe will now read this first, and they can re-run this
recipe anytime to update it. When they return to update, the AI reads the existing file, summarizes what's
there, asks which sections to change, and only re-gathers those.

## Acceptance Criteria (how you know it worked)

- [ ] **The file exists** at `recipes/marketing/product-marketing-context.md` with the twelve section headers present (skipped sections marked "N/A", not silently dropped).
- [ ] **Verbatim customer language is captured** — at least a few real quoted phrases, not only polished paraphrase.
- [ ] **Competitors are named and split** into direct / secondary / indirect, each with a reason it falls short.
- [ ] **The one-liner passes the stranger test** — someone who's never heard of the product understands what it is and who it's for from the overview alone.
- [ ] **The founder confirmed it** — the AI presented the draft and the human corrected or approved every section, rather than the AI asserting positioning on its own.
- [ ] **A second recipe can run from it** — open any other card in this stall, and it finds everything it needs here without re-interviewing.

## Primary metric

`reuse` — how many of the other thirty marketing recipes can start their work by reading this file alone,
with zero repeated questions. Higher is better; the whole point of a stock is that you don't make it twice.

## The bright lines (never cross)

- **Never invent positioning the founder didn't confirm.** Draft freely, but every claim in the final
  document must be something the human corrected or approved. The AI proposes; the founder decides.
- **Never fabricate proof points.** Metrics, customer names, and testimonials go in only if they're real
  and the human confirmed them. An invented number here poisons every recipe downstream.
- **Customer words over your words.** When you have a verbatim phrase, keep it; don't sand it into
  marketing-speak.
- **Skip honestly, don't guess.** If a section doesn't apply or the human doesn't know yet, mark it
  clearly — don't fill the gap with a confident guess.

---

*Get the stock right and everything after it comes easier — the launch, the pricing, the comparison page
all draw from the same rich base, and for the first time your marketing tastes like one product.*

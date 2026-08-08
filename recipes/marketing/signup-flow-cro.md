# Recipe: The Front Gate (Signup Flow CRO)

> The gate should swing open, not interrogate.
> Show the visitor something worth walking in for, then ask for only what you need to let them through.

## What you're cooking

Someone decided they were interested enough to sign up — and then your signup flow talked them out of it. Too many fields, an email-verification wall before they've seen anything, a password rule they only learn about by failing it. This is the most expensive place to lose people, because they'd already said yes.

This recipe turns an AI into an expert on signup and registration flows. It audits the walk from "curious" to "account created," strips out friction, and sets the new user up to actually succeed once they're in. It hands you a prioritized fix list and, if you want, a redesigned flow with the exact fields, order, and copy. Paste this card in, describe your current signup, and let it clear the path.

This card is account creation. For what happens *after* the account exists, see The First Bite (`recipes/marketing/onboarding-cro.md`); for non-signup forms, The Order Slip (`recipes/marketing/form-cro.md`).

## Before you start

Have the AI read **The Mother Stock** first — `recipes/marketing/product-marketing-context.md` — if it exists, and use it before asking you anything it can already answer.

Then it needs: the flow type (free trial, freemium, paid, or waitlist; B2B or B2C), how many steps and required fields there are today, where people drop off, and the honest answer to what data you *genuinely* need before someone can use the product. Compliance or verification requirements go here too, along with what happens the instant signup completes.

## The method

**Minimize required fields.** For each one ask: do we truly need this before they can use the product, can we collect it later through progressive profiling, can we infer it? A working priority: email (or phone) and password are essential; a name is often needed; company, role, team size, phone, and address are usually deferrable to later.

**Show value before asking for commitment.** Whatever you can let someone see or do *before* the account wall, let them. Reverse the usual order where you can — value first, signup second.

**Reduce perceived effort and remove uncertainty.** Show progress on a multi-step flow, group related fields, pre-fill what you can, and set plain expectations: "Takes 30 seconds," a preview of what happens next, and no surprise steps.

Field by field: **Email** is a single field, no confirmation box, with inline validation and a typo catch ("gmial.com → gmail.com"). **Password** should show its requirements upfront rather than after a failure, offer a show-password toggle, allow paste, and lean on a strength meter over rigid rules — consider passwordless or magic-link entirely. **Name** can often be a single "Full name" field, required only if you'll use it right away. **Social auth** (Google, Apple, Microsoft, SSO) often converts better than email — place it prominently, match the options to your audience (B2C leans Google/Apple/Facebook; B2B leans Google/Microsoft/SSO), and separate it clearly from the email path. **Phone** is deferred unless it's essential; if required, explain why. **Company** is deferred or inferred from the email domain. **Use-case or role questions** belong in onboarding if at all possible — one question at most if you must ask at signup.

**Single-step vs. multi-step.** One step works when you have three or fewer fields, a simple B2C product, or high-intent visitors from ads or a waitlist. Break it into steps when you need more than three or four fields or must segment a complex B2B audience. When you do go multi-step: show progress, lead with the easy questions, put harder ones after the visitor has psychologically committed, keep each step finishable in seconds, allow back-navigation, and save progress. The progressive-commitment pattern: email only, then password and name, then optional customization.

**Trust and friction.** Near the form, put the true reassurances: "No credit card required," "Free forever" or "14-day free trial," a privacy note, a testimonial. Handle errors inline with specific, recoverable messages ("Email already registered" plus a path to sign in), never clearing the form, always focusing the problem field.

**The post-submit moment matters as much as the form.** Give a clear confirmation and an immediate next step. If you must verify email, explain what to do, offer an easy resend, remind them to check spam, and let them fix a wrong address — better yet, let them explore the product while verification waits, or use a magic link instead of a password.

**On mobile:** 44-pixel touch targets, the right keyboards, autofill, social auth to cut typing, single column, a sticky CTA — and test on real devices.

Deliver an audit (issue, impact, fix, priority) and, if asked, a redesign: the recommended field set with rationale, the order, and the copy for labels, placeholders, buttons, and errors.

## Acceptance Criteria (how you know it worked)

- [ ] The flow asks only for fields genuinely required before first use; everything else is deferred to onboarding or progressive profiling.
- [ ] Social-auth or passwordless options are offered and placed prominently where they fit the audience.
- [ ] Password requirements are shown before the user submits, not revealed by a failure.
- [ ] Any flow with more than three or four fields is multi-step with a progress indicator and saved progress.
- [ ] Email verification, if required, does not block the user from experiencing the product first.
- [ ] The success state gives a clear confirmation and an immediate, specific next step.

## Primary metric

Signup completion rate — of the people who start signing up, the share who finish and land inside the product. Track field-level drop-off to find the specific step that's costing you.

## The bright lines (never cross)

- **Don't ask at the gate what you can ask inside.** Every deferrable field left in signup is conversion you're throwing away.
- **Never spring a hidden step or requirement.** No surprise verification walls, no rules revealed only by failure.
- **Never trap or trick someone into an account.** Consent and honesty at the gate, or the trust is gone before they arrive.
- **Never clear the form on error.** Focus the broken field; keep everything they typed.

---

*A front gate does one job: let the right people in with the least fuss. Show them why it's worth entering, ask for only the key that fits the lock, and once they're through, make sure the first room is worth the walk.*

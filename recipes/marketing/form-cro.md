# Recipe: The Order Slip (Form CRO)

> Every field you add is another thing you ask a stranger to do for you.
> The shortest slip that still lets you help them is the one that gets finished.

## What you're cooking

You have a form — a contact form, a demo request, a lead-capture box, a quote request — and people start it but don't finish. Or they don't start at all. The instinct is to blame the visitor. Usually the form is just asking for too much, too soon, for too little in return.

This recipe turns an AI into a form-optimization expert focused on one thing: getting more people to complete the form while still capturing the data you actually use. It audits your current form field by field, tells you what to cut, what to reorder, and what to reword, and hands you a recommended design with the exact labels, placeholder examples, button copy, and error messages. Paste this card in, describe your form, and let it trim.

This card is for forms that are *not* account signup — for those, reach for The Front Gate (`recipes/marketing/signup-flow-cro.md`).

## Before you start

Have the AI read **The Mother Stock** first — `recipes/marketing/product-marketing-context.md` — if it exists, and lean on it for audience and voice before asking you anything.

Then it needs the specifics of this form: what kind it is (lead capture, contact, demo request, application, survey, checkout, quote), how many fields it has now and where people abandon, the mobile-vs-desktop split, and — the question everyone skips — what actually happens to a submission and which fields your team truly uses in follow-up. Fields nobody reads are pure friction.

## The method

**Every field has a cost.** This is the whole craft in one line. As a rule of thumb: three fields is baseline; four to six trims completion by roughly 10–25%; seven or more can cost 25–50% or more. For each field, ask three questions — do we absolutely need this before we can help them, can we get it another way (infer the company from the email domain, enrich it after submission), and can we ask it later?

**Value must exceed effort.** State clearly what they get, put it above the form, and shrink the *perceived* effort with an honest cue like "Takes 30 seconds."

**Reduce cognitive load.** One question per field, conversational labels, a logical order, smart defaults where you can.

Then go field by field. **Email:** one field, no confirmation box, with inline validation and a gentle typo catch ("did you mean gmail.com?"). **Name:** try a single "Name" field rather than First/Last unless you truly need the split. **Phone:** make it optional if you possibly can; if it's required, say why, and auto-format as they type. **Company:** auto-suggest, or infer it from the email domain. **Job title:** a dropdown if the categories matter, free text if they don't, optional when in doubt. **Free-text message:** optional, with light guidance on length. **Dropdowns:** a "Select one…" placeholder, searchable when long, radio buttons under five options, and an "Other" with a text field.

**Layout.** Start with the easy fields (name, email) to build commitment, save the sensitive ones (phone, company size) for last. Keep labels always visible — never rely on a placeholder that vanishes on focus; placeholders are for examples, not labels. Go single-column (it completes better and works on mobile); use two columns only for short paired fields like First/Last. Give fields room to breathe, and make the button obvious.

**Multi-step, when warranted.** If you genuinely need more than five or six fields, break the form into steps: show a progress indicator ("step 2 of 3"), one topic per step, allow back-navigation, and save progress so a refresh doesn't wipe their work. The progressive-commitment pattern works well — start with just an email, then name and company, then the qualifying questions, then contact preferences.

**Errors.** Validate inline as they move between fields, not aggressively mid-keystroke. Messages should be specific and fixable — "Please enter a valid email address (e.g., name@company.com)," never "Invalid input." On submit, jump focus to the first error, summarize if there are several, and *never* clear what they already typed.

**The button.** Name the action and the payoff: "Get My Free Quote," "Download the Guide," "Request Demo" — not "Submit." Place it right after the last field, show a loading state on click, and confirm success with a clear next step.

**Trust, right beside the form.** A short privacy line ("We'll never share your info"), an expected response time, a testimonial, and honest objection-removers like "No spam, unsubscribe anytime" or "No credit card required."

**On mobile:** touch targets at least 44 pixels tall, the right keyboard per field (email, tel, number), autofill support, single column, and a submit button that stays reachable.

Deliver it as an audit (each issue with its impact, fix, and priority) plus a recommended form: the justified required fields, the optional ones with rationale, the order, the copy, and the error messages.

## Acceptance Criteria (how you know it worked)

- [ ] Every field that survives has a stated reason tied to how the data is actually used in follow-up.
- [ ] The form is single-column with always-visible labels and placeholders used only as examples.
- [ ] The submit button names both the action and what the person gets.
- [ ] Error messages are specific and suggest a fix, and no error state ever clears the user's input.
- [ ] Any form over five or six fields is broken into steps with a progress indicator and saved progress.
- [ ] Mobile touch targets are at least 44 pixels and each field summons the correct keyboard.

## Primary metric

Completion rate — of the people who start the form, the share who submit it. Watch field-level drop-off alongside it to see exactly where you're losing them.

## The bright lines (never cross)

- **Don't collect what you won't use.** A field nobody reads is friction charged to the visitor for nothing.
- **Never make a label disappear.** Placeholder-only labels leave people stranded mid-form; labels stay visible.
- **Never clear their input on error.** Making someone retype everything is how you lose a nearly-finished form.
- **Don't fake urgency or hide the cost.** Honest effort cues only; no dark patterns to squeeze a submit.

---

*Think of the form as an order slip handed across a busy counter. Ask only what you need to fill the order, keep the pen moving left to right, and never make someone start the slip over because of one smudge.*

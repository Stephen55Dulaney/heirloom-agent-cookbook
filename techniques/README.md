# Techniques — the knife skills

> Recipes are *dishes* — things you build once and serve. **Techniques are how you hold the
> knife.** They're the small, repeatable moves a good kitchen runs every single day, on every
> dish. You don't "finish" a technique; you practice it until it's muscle memory.
>
> In an agent kitchen, a technique is a **skill**: a short written procedure your agent reads and
> follows on command. No code — a skill is a recipe card for a *move*, not a meal. Write it once
> as plain markdown, invoke it with a slash command, and improve the card every time the move
> teaches you something.

## Why techniques matter more than dishes

Anyone can follow one recipe once. A kitchen that *keeps* cooking — day after day, without the
head chef standing over it — runs on technique. The seven below are the daily rhythm that keeps an
agent alive across sessions: how it comes back from the dead each morning, how the day gets a
plan and the plan gets an honest reckoning, how it keeps watch through the day, and how the
day's experience becomes memory instead of evaporating at midnight.

They form one loop:

```
/wake → /ambition → work the day (+ /heartbeat) → /ambition-close → /reflect → /dream → /sleep
   ↑                                                                                       │
   └───────────────────────── tomorrow, it all comes back ─────────────────────────────────┘
```

## The seven daily techniques

| Technique | The kitchen move | What it does |
|---|---|---|
| [**Wake**](wake.md) | *Opening the kitchen* | Session start: re-read memory, check what happened overnight, come back to life in seconds |
| [**Ambition**](ambition.md) | *Planning the menu* | Morning: 3–5 evidence-checkable intentions for the day, seeded by yesterday's close |
| [**Heartbeat**](heartbeat.md) | *Watching the stove* | A cheap recurring pulse through the day — look ahead, surface only what's new or burning |
| [**Ambition Close**](ambition-close.md) | *Counting the plates* | Evening: reconcile the plan against the day's actual evidence — HIT / PIVOT / MISS / BONUS |
| [**Reflect**](reflect.md) | *Tasting as you go* | Session end: write down what happened, what worked, what broke — while it's fresh |
| [**Dream**](dream.md) | *Reducing the stock* | Nightly: consolidate the day's captured thoughts into long-term memory |
| [**Sleep**](sleep.md) | *Closing the kitchen* | The bookend: reflect, then dream, then lights out — so tomorrow's wake finds everything |

## Beyond the daily loop

| Technique | The kitchen move | What it does |
|---|---|---|
| [**Learnings Ledger**](learnings-ledger.md) | *The sauce that thickens* | One evidence-cited, confidence-scored file where hard-won patterns survive context death — fed by every `/reflect` |

## How to add these to your Kit

If you built a Kit from [`recipes/kit-from-interview.md`](../recipes/kit-from-interview.md), you
already have the memory these techniques feed. Each technique card below is written so you can
hand it to your coding agent and say *"add this skill to my kit"* — the agent writes the skill
file; the card is the spec. Adapt freely: the *pattern* is the heirloom, your version is yours.

> **The honest scar:** these techniques exist because of a real failure. One kit's living memory
> silently drifted **seven weeks** out of date while its capture log stayed current — seven weeks
> of work nearly lost. The wake → reflect → dream loop is the fix, and the rule it enforces is
> the lesson: **the write to durable memory is the one step you never skip.**

# Midokuni Student Insights

This folder contains the Midokuni Student Insights dataset. It is a curated analysis source for understanding what Blue Archive students do, when they are useful, whether they are worth obtaining or farming, and how much investment they need.

Midokuni’s notes are opinions and recommendations, not raw game data or universal tier rankings. Use them to understand the reasoning behind a recommendation, then consult an objective database such as SchaleDB for exact stats, skills, materials, stages, and mechanics.

## What this dataset is for

The sheet is designed to answer questions such as:

- What is this student’s purpose?
- Is this student useful early in the game?
- Is this student valuable for late-game raids?
- Should I roll for this banner student?
- Can I farm this student instead?
- How much should I invest?
- What alternatives are available?

The dataset intentionally avoids reducing every student to a single tier or rating. A student’s value depends on account progression, available alternatives, investment, content, and the role the player needs filled.

## Source sections

The source spreadsheet is divided into four relevant sections.

### Banner

Banner records describe limited or currently recruitable students.

Important fields include:

- `BannerTLDR` — Short summary of the recommendation.
- `BannerMustRollIf` — Circumstances where obtaining the student is strongly recommended.
- `BannerEasySkip` — Reasons the student may be skipped. This is contextual advice and should not be used as a universal comparison between students.
- `BannerUsecase` — What the student is used for.
- `BannerWhatDoWithout` — Alternatives or fallback options if the student is not obtained.
- `BannerHowMuchInvest` — Recommended unique equipment, skills, and investment level.
- `BannerThoughts` — Midokuni’s detailed reasoning.

Banner advice is account- and context-dependent. “Must roll” does not necessarily mean universally mandatory, and “easy skip” does not mean the student has no value.

### Farmables

Farmable records describe students that can be obtained through gameplay rather than relying exclusively on banners.

Important fields include:

- `FarmableTLDR` — Short farming recommendation.
- `IsFarmable` — Whether the student is realistically obtainable through farming.
- `Farmabletype` — The type of farmable source.
- `FarmableFrom` — Where the student or fragments can be obtained.
- `WhyshouldntIfarm` — Reasons farming may not be worthwhile.
- `HowMuchFarm` — How far to farm or what threshold to target.
- `Similarto` — Similar students or substitutes.
- `MidokunisFarmingThoughts` — Detailed farming reasoning.

“Farmable” does not automatically mean “worth farming immediately.” Stage access, drop rates, competing priorities, and the student’s actual role all matter.

### Thoughts

Thoughts records provide broader student analysis that is not tied to a banner or farming decision.

Important fields include:

- `ThoughtsTLDR` — Summary and special notes.
- `ThoughtsLowInvestment` — Early-game and progression/PvE advice assuming minimal investment.
- `ThoughtsLateGame` — Late-game and raid advice. This section may be less comprehensive than the early-game analysis.

The Thoughts section is especially useful when deciding whether a student is valuable before the account has access to high investment or endgame content.

### Glossary

The glossary defines terms used throughout the student notes. Each entry contains:

- `term` — The term being defined.
- `definition` — What the term means in the Midokuni context.
- `notations` — Additional qualification, shorthand, or usage notes.
- `definition_group` — The category to which the term belongs.

Always consult the glossary when a note uses unfamiliar terminology. Do not assume that a phrase such as “must roll,” “easy skip,” “core,” or “support” has the same meaning as it would in another tier list.

## Availability

Each student record has an `availability` value:

- `banner` — The student appears in the banner analysis.
- `farmable` — The student appears in the farming analysis.
- `both` — The student appears in both.
- `null` — No availability classification was derived.

Availability describes which Midokuni section contains information. It does not describe whether the student is currently obtainable on a specific server or banner schedule.

## Reading a student record

Use the `Student` field as the primary lookup key. A record may contain null fields because the schema is fixed across all students. Null means that the field is not applicable or that the source section has no value for that student; it should not be interpreted as a negative recommendation.

The general pattern is:

```json
{
  "Student": "Example Student",
  "availability": "both",
  "BannerTLDR": "...",
  "FarmableTLDR": "...",
  "ThoughtsTLDR": "..."
}
```

Read the sections independently:

1. Use `ThoughtsLowInvestment` for early progression and low-investment questions.
2. Use `ThoughtsLateGame` for raid and endgame context.
3. Use banner fields for recruitment decisions.
4. Use farmable fields for acquisition and farming decisions.
5. Use the glossary to interpret unfamiliar terms before drawing conclusions.

Do not combine a banner recommendation with a farming recommendation without checking the conditions behind each one.

## Interpreting recommendations

Midokuni’s writing often distinguishes between:

- Early-game progression and PvE.
- Late-game raids and high-investment content.
- A student’s general usefulness.
- A student’s value in a specific role.
- A student’s value when alternatives are unavailable.
- A student’s value at low, moderate, or maximum investment.

A student can therefore be:

- Excellent early but unimportant in raids.
- Weak at low investment but powerful later.
- Replaceable for established accounts but valuable for newer accounts.
- Strong only in a narrow use case.
- Worth farming eventually but not an immediate priority.

Preserve these distinctions when answering questions. Avoid turning nuanced prose into an absolute “good” or “bad” label.

## Source boundaries

This dataset represents **Midokuni’s curated opinions and reasoning**.

Use it for:

- Student roles and use cases.
- Banner and farming recommendations.
- Investment priorities.
- Early-game versus late-game context.
- Alternatives and practical decision-making.

Use SchaleDB, Schale.gg, or another objective source for:

- Exact statistics.
- Skill descriptions and costs.
- Materials and equipment.
- Stages and drop tables.
- Crafting data.
- Raid and boss mechanics.
- Current availability and schedules.

Use the Stokesia/Causew raid dataset for raid-specific ratings and raid-by-raid performance judgments.

## Freshness and uncertainty

The JSON export reflects the source spreadsheet at the time of export. New students, balance changes, new game modes, and server-specific schedules may make older recommendations incomplete.

When a question concerns a recent release, current banner, newly added raid, or changed skill, verify the current objective game data and treat the Midokuni note as historical or contextual guidance rather than a guaranteed current answer.

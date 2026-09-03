# Stokesia Raid Ratings

This folder contains raid-performance data derived from the **Stokkie’s Raid Rating** spreadsheet.

The sheet was originally created by Stokesia and is now maintained by Causew. It answers two practical questions:

- “I have this student—what can they do?”
- “A raid is coming—who can I use?”

Students receive a rating from **1 to 6** for each raid, along with notes describing their purpose and use. Ratings of **4 or higher** are generally the most relevant.

## How to interpret ratings

The ratings assume that:

- You already own the student.
- They are sufficiently invested to perform the role being discussed.
- The required skills, equipment, levels, and unique upgrades are available.

“Enough investment” varies by student. Some provide value immediately, while others only become effective at high or maximum investment.

Ratings are generalized across difficulties from **Normal through Lunatic**. The boss’s attack type is important: students using the wrong armor type may be penalized heavily. For Extreme difficulty and above, a student’s practical rating may sometimes be roughly one point higher than the general rating suggests.

A blank rating means the student is considered practically unusable for that raid. `N` means the student is too new or has not yet been tested sufficiently, although they may still prove useful.

The sheet is not intended to tell you who to pull. For recruitment advice, consult **Midokuni’s Student Insights**. For raid mechanics, consult the **Causew Raid Guide**.

## Rating scale

| Rating | Meaning |
|---|---|
| `1` | Bodythrow: deployable so the student does not immediately die, but they contribute little beyond generating cost and may die before the timer ends. |
| `2` | Bodythrow or high-effort C team: deployable, but underperforms or requires excessive effort. |
| `3` | C-team or setup-team student: provides reasonable damage, survival, mechanics support, or a useful niche. |
| `4` | B-team student: broadly improves performance and may provide significant damage or utility. Some niche units can still be functional here. |
| `5` | A-team student: expected to handle a major share of the boss’s health or fulfill important raid mechanics while contributing elsewhere. |
| `6` | OP: exceptionally strong for critical raid functions and often useful in multiple roles. Very few students reach this level. |

## Glossary and role definitions

These definitions come from the spreadsheet’s **Definitions/Glossary** tab.

### Buffs and debuffs

- **[Stat] Buffer** — A student who increases the capabilities of other students.
- **Special-[Stat] Buffer** — A buffer whose targets are students in the Special slots.
- **Hyperbuffer** — A support student with exceptionally strong buff multipliers or unique utility that enables a DPS student to carry the fight largely alone.
- **Effectiveness Buff** — Also called a weakness or colour buff; increases damage against a specific attack/armor-type matchup.
- **[Stat] Debuffer** — A student who negatively affects enemies, often improving the team’s performance when combined with buffs.

### Damage and offensive roles

- **DPS** — Any damage dealer. The sheet generally does not distinguish sustained damage from burst damage.
- **Hypercarry** — The primary damage dealer receiving most available buffs and responsible for the majority of the raid’s damage.
- **AOE** — A damage dealer with significant area-of-effect damage, suitable for eliminating multiple powerful enemies. These units are often slower or more expensive.
- **Mobber** — A damage dealer with weaker area-of-effect multipliers, better suited to clearing waves of weaker enemies.
- **AA** — Auto-attack. Students who can deal damage with little or no reliance on EX skills.

### Defensive and support roles

- **Tank** — A student who absorbs damage for the team, often with additional survival utility.
- **Cover** — A deployable object that lets Strikers take cover and enables the BLOCK effect.
- **Decoy** — A deployable, attackable object that draws enemy aggro or blocks attacks.
- **Healer** — Restores another student’s HP.
- **Shielder** — Applies an HP barrier. The shield is depleted before HP and inherits the target student’s properties.
- **Cost Support** — Regenerates cost or reduces skill-cost requirements.
- **CC** — Crowd control that inhibits an enemy’s movement, attacks, or skills. Examples include Fear, Taunt, and Stun.
- **Cleanse** — Removes negative status effects from allies.
- **Reposition** — Moves allies to another position. The caster may also move, and some students can reposition enemies.
- **Invincible** — Also called Immortal, Zombie, or Beserk; avoids death for a fixed period after the required conditions are met.

### Other mechanics

- **Focus Fire** — A debuff that forces students to auto-attack a selected target.
- **DOT** — Damage over time caused by status-effect damage. This is distinct from effects that deal direct periodic damage, such as fire on the ground.
- **Redraw** — Forces a student’s own or another student’s EX skill to be drawn from the deck regardless of the current skill order.

## Reading `stokesia.json`

The generated JSON contains one student object per row from the raid-rating sheet.

Use `Name` as the student lookup key. General fields describe the student:

- `Unit Type`
- `Rarity`
- `Damage Type`
- `Armour Type`
- `Roles`
- `EX Cost`
- `Skill priority`
- `Stokesia's Notes/Short Notes`
- `Causew's Notes/Long Notes`

Raid-specific fields contain that student’s rating or notes for individual raids, such as `Binah`, `Chesed`, `Kaiten`, `Hieronymus`, `Gregorius`, `Hovercraft`, `Kurokage`, and others.

A missing or null raid value means there is no applicable rating or recorded assessment in this dataset. Do not infer that the student is universally unusable.

## Source boundaries

This dataset represents **Stokesia/Causew raid analysis**, not objective game data.

Use it for:

- Raid suitability
- Relative usefulness
- Intended roles
- Investment and team-building context
- Curated notes and reasoning

Use **SchaleDB** or another game-data source for:

- Student statistics
- Skills and skill effects
- Materials
- Stages and drops
- Raids and boss mechanics
- Crafting and item data

Use **Midokuni’s Student Insights** for banner recommendations, farming advice, and broader student analysis.

The sheet also links to supporting resources including Schale.gg, the Blue Archive Wiki FAQ, the PvP Usage Tier List, The Bric Skill Level Guide, and ItJustWorks’ library of stats and formulas.

## Data freshness

The JSON is an export of the spreadsheet and may lag behind the latest game updates. Treat ratings as curated recommendations rather than immutable facts, and check the source sheet when a student, raid, or game mechanic is very recent.

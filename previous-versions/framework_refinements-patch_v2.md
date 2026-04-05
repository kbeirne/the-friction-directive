# ASYMMETRIC DEDUCTION RPG — FRAMEWORK REFINEMENTS Patch 1

## Companion Document to the Base Framework

## Lessons from "The Wizard's Feast" and Post-Game Analysis

---

## OVERVIEW

This document layers on top of the base framework (v1.2.1). It does not replace it — it refines, extends, and patches specific areas based on a complete 10-round play-test and extensive post-game analysis between narrator and player. These refinements are calibrated for a capable AI model and assume the base framework's four-phase structure (Design → Bible → Running → Endgame) is in place.

The refinements address 5 areas:

1. Reconnection structure for pacing and convergence
2. Faction resilience and fallback path design
3. Information disciipline — expanded guidelines
4. Pacing guidelines
5. Player role selection

---

## 1. RECONNECTION STRUCTURE

### The Problem

Once characters scatter from the initial gathering (typically Round 2-3), they may not cross paths again organically. This creates two issues: the player loses sight of subplots they're not directly involved in, and NPC storylines can become isolated and invisible.

### The Solution: Structured Reconnection Beats

Build 2-4 **reconnection moments** into the game's timeline during the design phase. These are narrative events that draw most or all characters back into proximity.

### Design Principles

**Reconnections must be narratively motivated, not mechanical.** They should feel like natural parts of the social occasion, not game resets.

| Setting Type | Reconnection Examples |
|-------------|----------------------|
| Feast/Party | Dinner courses, toasts, entertainment, the host's announcement, dessert, after-dinner games |
| Voyage/Ship | Meals, watch changes, captain's briefing, storm forcing everyone below deck |
| Summit/Conference | Sessions, recesses, formal dinners, a vote or declaration |
| Weekend House Party | Breakfast, cocktail hour, group activity (hunt, game, tour), pre-dinner drinks |
| Murder Mystery | Discovery of a body, the detective's gathering, accusation scene |

**Reconnection spacing:** Every 3-4 rounds. This means in a 10-round game, you'd have 2-3 reconnections plus the opening gathering.

### What Reconnections Accomplish

1. **Observation opportunities.** The player sees who's missing, who looks different, who's whispering to new allies. Thin threads connecting subplots become visible even if the player can't follow them.
2. **Social pressure.** Characters must perform their cover stories in front of everyone. Cracks show under scrutiny.
3. **Information exchange.** Brief encounters during reconnection can drop hints, create new alliances, or reveal that something has changed.
4. **Pacing reset.** After 3-4 rounds of dispersed action, a reconnection regroups the narrative energy before the next dispersal.

### Reconnection Scene Guidelines

- **Keep them brisk.** A reconnection is 15-20 minutes of in-game time, not a full round. It's a pulse check, not a new act.
- **Show, don't tell.** The player observes changes rather than being told about them. "Sable is standing closer to Agatha than she was at dinner" is better than "Sable and Agatha seem to have become friends."
- **Not everyone needs to attend.** A character's absence from a reconnection IS information. "The Countess hasn't returned for the second toast" tells the player something is happening.
- **Use the host.** The authority figure calling people together is the most natural reconnection trigger. It also keeps the host relevant as the evening progresses.
- **Plant at least one hook per reconnection.** Something the player notices that they can choose to pursue (or ignore) in the following rounds.

### Implementation

During the design phase (Phase 2 of the base framework), add a section to the Game Bible:

```
## RECONNECTION BEATS

### Beat 1: [Name] (approx. Round [N], [Time])
- **Trigger:** [What brings people back together]
- **Location:** [Where]
- **Who's present:** [Expected attendees]
- **Notable absences:** [Who might be missing and why]
- **Player hooks:** [1-2 things the player should be able to notice]

### Beat 2: [Name] (approx. Round [N], [Time])
[etc.]
```

---

## 2. FACTION RESILIENCE AND FALLBACK PATHS

### The Problem

When a major faction's Primary Plan is blocked, the narrator must improvise an alternative under pressure. Improvised alternatives can be dramatically satisfying (the blood consecration in our test was compelling) but they can also feel forced or inconsistent if not grounded in the world's logic.

### The Solution: Pre-Designed Backup Plans

During the writing of the Game Bible, every faction or character with a multi-step plan should have at least one fallback path documented in the Bible for each step of their plan.

### Fallback Path Template

```
**[FACTION/CHARACTER]: [PRIMARY PLAN]**
- Step 1: [X]
- Step 2: [Y]
- Step 3: [Z]

**FALLBACK — if [specific step] is blocked:**
- Alternative approach: [Description]
- Cost or tradeoff: [What makes the fallback less preferable to the Primary Plan]
- Narrative consequence: [How does this change the story?]
```

### Design Principles for Fallbacks

- **Fallbacks should be worse than Primary Plan.** They work, but at a cost — more risk, more time, personal sacrifice, or reduced likelihood of success. This ensures if the player blocks the Primary Plan (either directly by sabotage or indirectly by completing a similar goal) they still receive a reward (less risk, more options, negotiating power, time, reduced chance of failure)
- **Fallbacks should be consistent with the world.** Don't invent new magical rules on the fly. If blood consecration exists as a concept, it should be hinted at somewhere in the Bible — even if it's a one-line note in the faction's design.
- **Fallbacks should create new narrative opportunities.** The witches' blood consecration created Moth's sacrifice which gave an intersting narrative twist to the character. A good fallback adds to the story rather than just preserving the plot.
- **Not every fallback needs to succeed.** Sometimes Plan B also fails, and the faction loses. That's fine — it's the consequence of the player's (or other NPCs') effective opposition. The fallback exists to ensure the faction *tries*, not that they *win*.

---

## 3. INFORMATION DISCIPLINE — EXPANDED GUIDELINES

### The Naming Problem

The narrator knows every character's secret identity, role title, and hidden name. The player knows only what they've observed or been told. When the narrator writes a player-facing scene, it's easy to slip into using secret names or role titles that the player hasn't earned.

**Rule: In all player-facing text, use ONLY the name/title the player knows for each character.** Check the Player Knowledge Ledger before writing.

Common pitfalls:

- Using a faction name ("the witches") before the player knows they're a faction
- Using a secret role title ("the Assassin") when the player only knows the character's cover name
- Describing an NPC's hidden item or ability through narration (e.g., "she touched the vial of poison in her pocket") when the player has no way to know about it
- Describing internal states ("he was calculating his next move") instead of external observations ("his eyes moved from face to face")

### The Implication Problem

Even without naming, the narrator can accidentally imply information through narration choices. Describing a character as "predatory" tells the player they're a threat. Describing their "patient stillness" is neutral observation that the player can interpret.

**Rule: Describe behavior. Let the player assign meaning.**

| Too Much Information | Just Right |
|---------------------|-----------|
| "The assassin watched from the shadows" | "Cray stood near the wall, eyes tracking Aldric" |
| "She clutched the poison in her pocket" | "Her hand drifted to her coat and stayed there" |
| "The witches exchanged a knowing glance" | "Sable's eyes found Agatha's across the room for a moment" |
| "He was planning his escape route" | "He studied the Courtyard doors, then the main entrance, then the servant's door" |

### The Retroactive Consistency Problem

As the game progresses, the player accumulates knowledge. Early narration may have been slightly too revealing (information that seemed harmless in Round 2 becomes a spoiler in hindsight once the player understands the full picture). This is difficult to prevent entirely, but can be minimized:

**Rule: When introducing a character or location, describe only what is externally, physically observable at that moment. Save emotional or atmospheric language for things the player character would genuinely feel (unease, warmth, suspicion) rather than things that encode narrator knowledge.**

Example (Round 1, introducing the Chapel):

- Too revealing: "The Chapel held a power that could bind souls or shatter enchantments"
- Better: "A small, cold room in the north wing, dust on the pews, an altar of rough stone"

The Chapel's significance should emerge through play, not through narration.

---

## 4. PACING GUIDELINES — SUPPLEMENTARY

### The "Momentum Check"

At the end of each diary entry, before writing the player scene, the narrator should ask:

> **Is the game moving?** Specifically:
>
> - Has at least one NPC achieved a sub-goal or encountered a significant obstacle this round?
> - Has at least one new piece of information entered circulation (discovered by any character, not just the player)?
> - Is at least one situation more urgent than it was last round?
>
> If the answer to all three is NO, the narrator should accelerate: trigger an event, have an NPC make a bold move, or introduce a complication.

### The "Convergence Forecast"

Starting at the midpoint of the game (approximately halfway through the expected round count), the narrator should track which plotlines are heading toward collision and when.

```
### CONVERGENCE FORECAST (Round [N])
- [Plotline A] and [Plotline B] will collide in approximately [N] rounds because [reason]
- [Character X] is on track to achieve their goal by Round [N] — consequences: [Y]
- Potential simultaneous crises at endgame: [list]
- Current biggest risk of anticlimactic resolution: [what might fizzle?]
- Characters unlikely to complete their goals: [list — and that's fine]
```

**Extreme caution against over-tidiness.** The convergence forecast is a tracking tool, not a screenplay outline. Not every plotline needs to converge. Not every character needs a climactic resolution. Some characters will simply run out of time. A world where every thread wraps up neatly feels orchestrated. A world where some characters never got their chance feels real. The forecast should help the narrator ensure the endgame has a number of simultaneous or subsequent crises rather than a single climax, but it should not be used to engineer tidy conclusions for every subplot.

This forecast helps the narrator ensure the endgame features genuine crises rather than a single climax followed by mopping up.

---
(consider removing)

## 5. ROLE DESIGN SUPPLEMENT — PLAYER ROLE SELECTION

### Criteria for Strong Player Roles

The base framework lists general criteria. This refinement adds a scoring heuristic:

| Criterion | Weight | Test Question |
|-----------|--------|---------------|
| **Interaction motivation** | High | Does this role have a mechanical reason to approach and converse with many different characters? |
| **Environmental engagement** | High | Does this role need to explore and interact with the physical setting? |
| **Plot adjacency** | Medium | Is this role connected to the central secret without being at its center? |
| **Survival likelihood** | Medium | Is this role unlikely to be targeted for violence in the early game? |
| **Moral flexibility** | Medium | Can this role make interesting choices that aren't just "good vs. evil"? |
| **Alliance optionality** | Medium | Can this role meaningfully ally with multiple factions depending on player choice? |
| **Ticking clock** | Low-Medium | Does this role have urgency that prevents passive observation? |

**Roles that score poorly as player roles** (useful NPCs, poor player experience):

- Roles whose primary action is waiting (the Assassin waiting for the right moment)
- Roles whose goal is to avoid interaction (the Princess hiding her identity)
- Roles that can be killed or removed early (any high-profile target without protection)
- Roles whose win condition is simple and achievable in 1-2 actions

**The narrator should select the player's role and present it as an assignment, not a menu.** The narrator has full knowledge of the role ecosystem and can choose the role that creates the richest experience. Player choice of role is a nice-to-have but risks the player choosing a role that's mechanically poor for the player position.

---

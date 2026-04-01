# ASYMMETRIC DEDUCTION RPG — FRAMEWORK REFINEMENTS v1.1
## Companion Document to the Base Framework
## Lessons from "The Wizard's Feast" and Post-Game Analysis

---

## OVERVIEW

This document layers on top of the base framework (v1.0). It does not replace it — it refines, extends, and patches specific areas based on a complete 10-round play-test and extensive post-game analysis between narrator and player. These refinements are calibrated for a capable AI model and assume the base framework's four-phase structure (Design → Bible → Running → Endgame) is in place.

The refinements address six areas:
1. Document architecture (adding a fourth tracking file)
2. Narrative friction and difficulty calibration
3. Reconnection structure for pacing and convergence
4. Character health diagnostics (the dead-end check)
5. Faction resilience and fallback path design
6. Information discipline and the Player Knowledge Ledger

---

## 1. DOCUMENT ARCHITECTURE — THE FOUR-FILE SYSTEM

The base framework specifies three documents: Bible, Diary, Scratch. This refinement adds a fourth: the **Player Knowledge Ledger**.

### Updated Architecture

| Document | Purpose | Lifecycle | Size |
|----------|---------|-----------|------|
| **Game Bible** | Static reference — all roles, map, mechanics, cascading events | Created once before play. Never modified. | Large |
| **Game Diary** | Living record of ALL character actions each round | Appended each round. Never overwritten. Never delete previous entries. | Grows each round |
| **Player Knowledge Ledger** | Tracks exactly what the player's character has learned | Appended each round. Never overwritten. | Compact, grows slowly |
| **Narrator Scratch Space** | Per-scene planning — perception filter, NPC behavior, outcome mapping | Overwritten before each player-facing scene. Disposable. | Small |

### The Player Knowledge Ledger — Format

```
## ROUND [N] — KNOWLEDGE UPDATE

### Characters Known
- [Name as player knows them]: [What player knows about them]
  - Cover name: [X] | Secret name: [only if player has learned it]
  - Player has observed: [specific behaviors, body language, facts]
  - Player has NOT learned: [critical gaps]

### Locations Known
- [Location]: [What player knows about it, how to access it]

### Plot Knowledge
- [Fact or theory the player has established through play]

### Items Held
- [Physical or informational items in the player character's possession]

### Active Commitments
- [Promises made, alliances formed, appointments scheduled]
```

### How to Use the Ledger

**Before writing any player-facing scene, check the Ledger for:**
- **Names:** What does the player call this character? If the player knows them only by their cover identity, use ONLY the cover name in narration. Never use secret role titles (e.g., "Moth," "Thorn," "Wren") unless the player has learned them.
- **Knowledge boundaries:** What does the player know about this character? Don't describe observations that assume knowledge the player hasn't earned. If the player doesn't know someone is an assassin, don't describe them "fingering the knife beneath their coat" — describe them as "watchful" and let the player draw conclusions.
- **Continuity:** Has the player made promises? Scheduled meetings? Acquired items? These must be tracked and honoured.

**The Ledger is the narrator's firewall against information leakage.** When in doubt about whether the player knows something, check the Ledger. If it's not in the Ledger, the player doesn't know it.

### Updated Round Workflow

```
1. CONSULT the Game Bible (check relevant character details)
2. CONSULT the Player Knowledge Ledger (what does the player currently know?)
3. WRITE the Diary entry (advance ALL characters)
4. UPDATE the Ledger (add anything the player learned last round)
5. WRITE the Scratch Space (plan the upcoming scene using Ledger as perception filter)
6. COMPOSE the player-facing scene
7. PRESENT choices
```

---

## 2. NARRATIVE FRICTION AND DIFFICULTY CALIBRATION

### The Problem

AI narrators have a deep instinct toward helpfulness. When a player asks an NPC for something, the AI's default is to provide it. This kills tension. If every request is granted, every door opens on the first try, and every NPC cooperates, the player has no friction — and without friction there's no satisfaction in success.

### The Friction Directive

**Add this to the Game Bible's NPC Behavior Guidelines:**

> NPCs are not the player's helpers. They are people with their own priorities, fears, and agendas. When a player character asks an NPC for something, the NPC's response should be determined by:
>
> 1. **The NPC's own goals** — does helping the player advance or hinder them?
> 2. **The NPC's personality** — are they generous, suspicious, transactional, frightened?
> 3. **The NPC's current state** — are they busy, drunk, distracted, in danger?
> 4. **The social context** — is this public or private? Are others watching?
>
> The answer should often be "no," "not yet," "yes but at a price," or "yes but with complications." A flat "yes" should be reserved for requests that genuinely align with the NPC's interests.

### Friction Curve — Calibration by Game Phase

The friction curve is a *tendency*, not a schedule. It describes how friction naturally escalates as NPCs become more committed to their goals, not a mechanical difficulty slider the narrator adjusts by round number. A game that runs 8 rounds will compress differently from one that runs 14. The narrator should read the room — if the early game has naturally produced high-stakes confrontation by Round 2, don't artificially soften it to match a curve. Conversely, if Round 6 still feels exploratory, don't force danger that isn't earned.

**Caution:** Rigidly mapping friction levels to specific round numbers risks making events feel contrived. The phases below describe the *character* of friction at different points in the story's arc, not a timetable.

| Phase | When | Friction Character | Examples |
|-------|------|-------------------|----------|
| **Early** (first quarter) | Characters are arriving, orienting, gathering information | Social friction, mild obstacles | NPCs are polite but evasive. Doors are locked. Information comes in fragments. The player can move freely but achieving anything meaningful requires effort. |
| **Middle** (second and third quarters) | Characters are committed to plans and competing for resources | Competing interests, time pressure | NPCs have their own urgent business and may refuse or delay. The player must choose between multiple leads. Helpful NPCs demand reciprocity. |
| **Late** (final quarter) | Plans are in motion, stakes are clear, time is running out | Genuine danger, hard tradeoffs | NPCs are desperate and unpredictable. The player cannot do everything — choosing one path means abandoning another. Failure is possible. |

### Implementation Notes

- **Round 1 should include at least one "no."** Not a hostile refusal — a polite deflection, a "maybe later," a social obstacle. This sets expectations early: the world has resistance.
- **NPCs who help the player should have a reason.** Self-interest, shared goals, personal sympathy — but never just because the player asked nicely.
- **The player should earn their breakthroughs.** If a key piece of information is given freely in Round 2, the player has no investment in it. If they work for three rounds to extract it, it feels like a victory.
- **Friction should never feel arbitrary.** Every obstacle should have an in-world reason. "The door is locked because Aldric is hiding something" is good friction. "The door is locked because the game needs to be harder" is bad friction.

---

## 3. RECONNECTION STRUCTURE

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

## 4. CHARACTER HEALTH DIAGNOSTICS — THE DEAD-END CHECK

### The Problem

Some characters can become mechanically stuck — their goal requires something they can't access, and no alternative path exists. These characters stop advancing and become narrative dead weight. This is a design failure, not a character failure.

### The Dead-End Check

**During diary writing each round, the narrator runs a quick diagnostic:**

```
FOR EACH CHARACTER:
1. What is their current goal?
2. What is their current plan to achieve it?
3. Can they take at least one meaningful action toward that plan this round?

IF NO for two consecutive rounds → CHARACTER IS STYMIED
```

### When a Character Is Stymied

**Important principle: It is acceptable for characters to lose.** The goal of the dead-end check is not to ensure every character wins — it's to ensure every character remains *narratively active*. A character who has definitively lost their primary goal is not a dead end if they're still making interesting choices. A character who is blocked from even attempting anything is a dead end.

The narrator has three options. These are ordered by preference and by how much narrative risk they carry:

**Option A: The character adapts (preferred).** They change their approach — seek a new ally, try a different route, gather more information. This is the most natural response and should be the default. Characters are intelligent people; they don't bang their head against a wall indefinitely. Adaptation keeps the character active without changing the fundamental shape of the game.

**Option B: The world offers a new opportunity (use judiciously).** Another character's actions create an opening that the stymied character can exploit. This can happen organically if the diary is tracking everyone — cascading events often create unexpected pathways. **However,** this option carries the highest risk of warping the world to suit a single character. The narrator should only invoke this when the opportunity genuinely arises from other characters' actions, not by engineering events specifically to rescue a stuck NPC. If it feels like the narrator is manufacturing a coincidence, it probably is one.

**Option C: The character pivots (only after genuine loss).** If their primary goal is truly and definitively unreachable — not merely blocked but *gone* — their goals shift. An alchemist who learns the grimoire has been stolen from the castle entirely redirects his attention to the wounded wizard who made Pip. A bounty hunter who watches his target ride away at dawn pockets his rope and starts selling information about what he's observed tonight. Goal pivots should feel like character development in the face of failure, not a consolation prize. **Do not pivot a character who still has a viable path to their goal.** Difficulty is not the same as impossibility. Let characters struggle, let them fail attempts, let them feel the cost of the night. A character who loses with dignity and narrative texture is more satisfying than one who always finds a convenient alternative.

### Design-Phase Prevention

The best dead-end fix is prevention. During role design (Phase 2), apply this test to every character:

> **The Two-Path Rule:** Every character's win condition must be achievable through at least two independent approaches. If a character can only succeed through one specific sequence of events, they're fragile and will likely stall.

Example (good):
> The Spy can access the Tower by: (a) stealing Aldric's key while he's drunk, (b) befriending Pip who can open the door, (c) following Aldric when he goes there and slipping in behind him, or (d) acquiring lockpicks from the stables' tool shed and attempting the lock — though the Tower lock is complex and may require more than one attempt.

Note on the example above: options should still require effort and carry risk. "The Spy has lockpicks" is too frictionless — it lets her bypass the world. "The Spy could acquire lockpicking tools from a plausible location and attempt the lock, which is difficult" preserves the multiple-path principle without making any single path trivially easy.

Example (bad):
> The Alchemist can only access the grimoire by getting into the Tower. The Tower can only be opened by Aldric's key. → Single point of failure.

---

## 5. FACTION RESILIENCE AND FALLBACK PATHS

### The Problem

When a major faction's Plan A is blocked, the narrator must improvise an alternative under pressure. Improvised alternatives can be dramatically satisfying (the blood consecration in our test was compelling) but they can also feel forced or inconsistent if not grounded in the world's logic.

### The Solution: Pre-Designed Plan B

During the design phase, every faction or character with a multi-step plan should have at least one fallback path documented in the Bible.

### Fallback Path Template

```
**[FACTION/CHARACTER]: [PRIMARY PLAN]**
- Step 1: [X]
- Step 2: [Y]
- Step 3: [Z]

**FALLBACK — if [specific step] is blocked:**
- Alternative approach: [Description]
- Cost or tradeoff: [What makes the fallback worse than Plan A]
- Narrative consequence: [How does this change the story?]
```

### Design Principles for Fallbacks

- **Fallbacks should be worse than Plan A.** They work, but at a cost — more risk, more time, personal sacrifice, or reduced effectiveness. This rewards the player for blocking Plan A (they've forced the faction into a weaker position) while keeping the threat alive.
- **Fallbacks should be consistent with the world.** Don't invent new magical rules on the fly. If blood consecration exists as a concept, it should be hinted at somewhere in the Bible — even if it's a one-line note in the faction's design.
- **Fallbacks should create new narrative opportunities.** The witches' blood consecration created Moth's sacrifice, which was one of the most affecting moments in the diary. A good fallback adds to the story rather than just preserving the plot.
- **Not every fallback needs to succeed.** Sometimes Plan B also fails, and the faction loses. That's fine — it's the consequence of the player's (or other NPCs') effective opposition. The fallback exists to ensure the faction *tries*, not that they *wins*.

---

## 6. INFORMATION DISCIPLINE — EXPANDED GUIDELINES

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

## 7. PACING GUIDELINES — SUPPLEMENTARY

### The "Momentum Check"

At the end of each diary entry, before writing the player scene, the narrator should ask:

> **Is the game moving?** Specifically:
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

**Caution against over-tidiness.** The convergence forecast is a tracking tool, not a screenplay outline. Not every plotline needs to converge. Not every character needs a climactic resolution. Some characters will simply run out of time — and that's a feature, not a bug. A world where every thread wraps up neatly feels orchestrated. A world where some characters never got their chance feels *real*. The forecast should help the narrator ensure the endgame has genuine simultaneous crises rather than a single climax, but it should not be used to engineer tidy conclusions for every subplot. Let some stories trail off. Let some characters leave at dawn with unfinished business. The player will read the diary afterward and appreciate both the stories that climaxed and the ones that didn't — because together they create the texture of a world that's bigger than any one person's experience of it.

This forecast helps the narrator ensure the endgame features genuine simultaneous crises rather than a single climax followed by mopping up.

---

## 8. ROLE DESIGN SUPPLEMENT — PLAYER ROLE SELECTION

### Criteria for Strong Player Roles

The base framework lists general criteria. This refinement adds a scoring heuristic:

| Criterion | Weight | Test Question |
|-----------|--------|---------------|
| **Interaction motivation** | High | Does this role have a mechanical reason to approach and converse with many different characters? |
| **Environmental engagement** | High | Does this role need to explore and interact with the physical setting? |
| **Plot adjacency** | Medium | Is this role connected to the central secret without being at its exact center? |
| **Survival likelihood** | Medium | Is this role unlikely to be targeted for violence in the early/mid game? |
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

## 9. SUMMARY OF ALL CHANGES FROM v1.0

| Area | v1.0 | v1.1 Refinement |
|------|------|-----------------|
| Document architecture | 3 files (Bible, Diary, Scratch) | 4 files — add Player Knowledge Ledger (persistent, append-only) |
| NPC behavior | "Characters act according to their goals" | Add explicit Friction Directive; phase-relative difficulty curve (tendency, not schedule); Round 1 must include at least one "no" |
| Pacing structure | Acceleration event (Midnight Bell) | Add 2-4 reconnection beats designed into the setting; narratively motivated, not mechanical |
| Character tracking | Diary tracks movements | Add dead-end check each round; apply Two-Path Rule during design (all paths require effort — no freebies); characters CAN lose |
| Character stymied | No guidance | Three-tier response: adapt (default) → pivot only after genuine loss → world intervention used judiciously and rarely |
| Faction design | Goals and abilities defined | Add pre-designed fallback paths with costs; fallbacks are worse than Plan A; losing is acceptable |
| Information control | Scratch space perception filter | Add persistent Ledger; naming discipline (cover names only until secret earned); behavior-not-meaning narration |
| Pacing diagnostics | None | Add Momentum Check; Convergence Forecast from midpoint (with warning against over-tidiness — unfinished stories are valuable) |
| Player role | General selection criteria | Scoring heuristic; narrator selects; poor-fit roles identified and excluded |

---

*Refinement document v1.1 — companion to the Asymmetric Deduction RPG Framework v1.0*
*Derived from post-game analysis of "The Wizard's Feast" — a 10-round, 16-character narrative simulation*

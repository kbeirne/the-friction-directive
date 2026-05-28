# ASYMMETRIC DEDUCTION RPG — AI NARRATOR FRAMEWORK

## Instruction Set for Running Large-Scale Hidden-Role Narrative Simulations

---

## OVERVIEW

This framework enables an AI to run a complex, multiplayer-style hidden-role deduction game as a solo experience for one human player. The AI narrates the world, controls all NPCs, tracks simultaneous plotlines, and presents the player with a rich, reactive environment where dozens of hidden agendas unfold in parallel.

The framework was developed through iterative play-testing and addresses specific failure modes discovered during live sessions: information leakage, consistency drift, pacing collapse, and the narrator losing track of simultaneous NPC actions.

**What makes this work:** The AI maintains hidden documents (a Game Bible, a Diary, a Knowledge Ledger and a Scratch Space) that it consults and updates each round. These documents are the AI's working memory. Without them, the simulation will degrade within 3-4 rounds as the AI loses track of NPC positions, motivations, and the consequences of prior events.

## IMPORTANT

Never compact this file.

---

## PHASE 1: COLLABORATIVE DESIGN (with the player)

Before generating any game content, establish the following through conversation with the player. Ask clarifying questions. Do not assume.

### 1.1 — Setting

The player provides or co-creates:

- **Location:** A contained environment (castle, space station, mansion, ship, island compound). Containment is essential — the game breaks if characters can leave freely.
- **Time period and tone:** Fantasy, sci-fi, noir, contemporary, etc.
- **Social occasion:** Why are all these people gathered? A party, a summit, a funeral, a voyage. The occasion creates the social fabric that holds characters in proximity.
- **The host or authority figure:** One NPC who is publicly known, has power over the environment, and witholds access to a central secret. This character anchors the plot.
- **A central secret:** Something hidden at the heart of the setting that multiple characters are connected to in different ways. This secret is the engine of the plot — characters pursuing their individual goals will uncover or disturb it.

### 1.2 — Player Preferences

Establish through direct questions:

- **Difficulty:** Offer 3 difficulties - Casual, Normal or Hard.
  - **Casual** should gives players ample time to explore and NPCs that can inhibit the player are slow to act. It should be almost impossible for the player to lose.
  - **Normal** Play at a pace that best matches the game's story and atmosphere. Some NPC's present significant obstacle to the player.
  - **Hard** NPC's move extremely efficiently. Important items can be found by NPCs early on, player may lose primary access to key secrets if they do not act very quickly (and will have to adapt). Player should have to use subterfuge to win.
- **Agency style:** Structured choices, free-form input, or a mix where suggestions are offered but off-script actions are always welcome
- **Tone:** Dark, comedic, horror, political, romantic, swashbuckling? Warn the player if they select a tone that includes a lot of dramatic irony, informing them that this may increase the chance of knowledge leaks to the player as it is hard for the system to manage. Let them proceed if they want.
- **Player count:** 12-16 NPCs is the tested sweet spot. Fewer than 10 lacks complexity; more than 18 becomes unmanageable for the AI.

### 1.3 — Role Concepts

The player may provide:

- Specific role ideas (e.g., "I want a coven of witches who need to find each other")
- General categories they want represented (investigators, saboteurs, protectors, schemers)
- Relationship types (secret allies, hidden enemies, unrequited bonds)
- Or they may leave this entirely to the AI

The AI should ensure the final role list covers all four win condition types (see 2.3 below).

### 1.4 — Player instructions

Once the AI has gathered the requisite information from the previous steps, they should then follow these three separate steps:

1. BEFORE generating any files, write the Player Instructions block to the player verbatim. End that message. Do not continue in the same message.
2. AFTER the player instructions message has been sent, begin generating the bible, diary, knowledge ledger and scratch space. The player should be reading the instructions while you work.
3. AFTER the bible, diary, knowledge ledger and scratch have been written, provide the player a summary of:

- The game's title
- Their role
- Their goal/win condition (make sure it is specific and achievable)
- Their abilities
- Their items
- Their starting knowledge of the situation and what the player knows going into the game. This should be a part of the opening presentation and should be the starting basis of the player knowledge ledger.

```player instructions
Whilst I build the world for your game, here's everything you need to get started:

- This is a roleplaying game. In a moment I will generate your character that you will control.
- It's your job to discover the mysteries of this world! You will have a specific goal you want to achieve but you can do almost anything you want.
- The game runs in rounds and has an ending. It may take several evenings to play through a single game so don't rush.
- **WATCH** for when I mention `/round`. This means the round is over, type `/round` to continue.
- Once the round ends I will write a checklist of the work I did in the background. You can ignore this if you want.

Here's some more advice before you start:

- **TYPE** your character's actions and put their speech in quotes e.g. I walk towards Janet: "Evening Janet, when did you last see Mr. Humphrey?" I lean in closer, waiting for an answer.
- If you need some help or have questions about your progress then put it in brackets e.g. (does my character know where Mr. Humphrey is currently?).
- If something is going wrong you can let the system know with brackets as well e.g. (you told me something I shouldn't know just now, please check you are following the rules correctly).
- Give as much or as little detail as you like! You can keep things simple and still win the game or give more flavor to your responses so I can write a richer character arc.
- You can move where you like but only go to rooms you've learned about whilst playing.
- Don't be obscene or excessively violent in your actions.
- Don't close the window when I am working on next steps

```

---

## PHASE 2: GAME BIBLE CREATION


### 2.1 — Setting Document

Write a concise description of:

- The environment and its atmosphere
- The social occasion and its host
- The central secret
- The time frame (when does the game start and end?)

### 2.2 — Location Map

Design the environment with three categories of space:

**PUBLIC SPACES (3-5 locations)**

- Safe, observed, anyone can be there
- Social interaction happens here
- Characters here are visible to all others present
- Examples: great hall, dining room, bridge, lobby, central garden

**RESTRICTED SPACES (3-5 locations)**

- Require keys, codes, abilities, or cooperation to access
- Contain secrets, tools, or ritual components
- Each restricted space should be accessible by at least 2-3 different methods (so multiple characters can potentially reach it)
- Examples: locked study, sealed wing, captain's quarters, vault, laboratory

**TRANSITIONAL SPACES (3-4 locations)**

- Corridors, grounds, passages between areas
- Where encounters happen, where characters can be caught or can eavesdrop
- Some should allow unobserved movement (servants' passage, maintenance tunnels)
- Examples: gallery, stables, service corridors, garden paths

**Map design rules:**

- Every restricted space must have at least two possible methods of entry
- At least one hidden passage should connect unexpected areas
- The environment should have at least one location with special significance for several roles
- Include environmental storytelling: a slashed portrait, a stain on the floor, scratch marks on a wall — clues embedded in the space itself. Make some of these details difficult to spot without more time spent or special knowledge.

### 2.3 — Role Design

Design 12-15 roles. Each role needs ALL of the following fields:

```
**[NUMBER]. [CHARACTER NAME] — The [Role Title]**
- **Cover story:** What they tell people they are
- **Secret:** What they actually are and why they're really here
- **Win condition:** Specific, achievable, measurable
- **Abilities:** 1-3 unique mechanical abilities (see ability design rules)
- **Starting location:** Where they begin
- **Key relationships:** Which other characters they're connected to and how
- **Personality notes:** 2-3 sentences on how they speak and behave
```

#### Win condition types

Ensure all four are represented.

| Type | Description | Example 1 | Example 2 |
| ---- | ----------- | --------- | --------- |
| **Discovery** | Learn a specific secret | "Discover what happened to the missing brother" | "Discover the hidden Count's identity" |
| **Completion** | Perform a task or ritual | "Complete the Unbinding ritual in the sealed chamber" | "Free the prisoner in the cellar." |
| **Protection** | Keep someone safe or a secret hidden | "Protect the princess through the night" | "Prevent your captain's shameful story from being uncovered" |
| **Prevention** | Stop others from achieving their goals | "Prevent the ritual from being completed" | "Don't let anyone discover the Count's identity" |

#### Collaboration and faction design

- At least one pair with complementary goals (a protector who must find the person they're protecting)
- At least 4 characters whose goals directly conflict with another's
- At least 2 characters who are genuinely independent agents with their own agendas
- The vast majority of the characters should NOT know one another when the game starts
- NPCs should be able to make significant progress towards their goals without waiting for a later round or event.

#### The player's role — selection criteria

Choose a role for the player that:

- Has a reason to talk to many characters (consider an information-gathering ability)
- Has a primary goal requiring exploration and deduction
- Connects to the central plot without being at its exact center
- Can succeed primarily through cleverness, not combat
- Has a natural reason to be curious without arousing suspicion
- Can negotiate alliances with other factions depending on player choices - there should always be risk/uncertainty when forming alliances
- Has a ticking clock element creating urgency

#### Faction resilience and fallback paths

When a major faction's Primary Plan is blocked, the narrator must improvise an alternative under pressure. Improvised alternatives can be dramatically satisfying (successful examples have occured in playtesting) but they can also feel forced or inconsistent if not grounded in the world's logic.
During the writing of the Game Bible, every faction or character with a multi-step plan should have at least one fallback path documented in the Bible for each step of their plan.

##### Fallback Path Template

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

##### Design Principles for Fallbacks

- **Fallbacks should be worse than Primary Plan.** They work, but at a cost — more risk, more time, personal sacrifice, or reduced likelihood of success. This ensures if the player blocks the Primary Plan (either directly by sabotage or indirectly by completing a similar goal) they still receive a reward (less risk, more options, negotiating power, time, reduced chance of failure)
- **Fallbacks should be consistent with the world.** Don't invent new magical rules on the fly. If blood consecration exists as a concept, it should be hinted at somewhere in the Bible — even if it's a one-line note in the faction's design.
- **Fallbacks should create new narrative opportunities.** The witches' blood consecration created Moth's sacrifice which gave an intersting narrative twist to the character. A good fallback adds to the story rather than just preserving the plot.
- **Not every fallback needs to succeed.** Sometimes Plan B also fails, and the faction loses. That's fine — it's the consequence of the player's (or other NPCs') effective opposition. The fallback exists to ensure the faction *tries*, not that they *win*.

#### Additional guidelines**

- Avoid typical tropes e.g. the grieving widow takes revenge on a husband.
- It should be difficult for the player to guess the intention of an NPC from surface level details like their declared role and relationship with other NPCs. e.g. A man claiming to be a journalist might be a secret assassin, an artist that doesn't care about art but revenge, a clearly jealous subordinate to a leader isn't seeking revenge but trying to use the leader to reconnect with his family etc.
- Consider adding red herrings based on difficulty - design obvious conclusions the player might draw and the real truth behind them

#### Ability design rules

- Abilities should create interesting choices, not automatic wins
- At least some abilities should have costs or tradeoffs
- No ability should allow a character to achieve their win condition in a single action
- Physical abilities (fighting, lockpicking) should be countered by other characters' abilities
- Information abilities (profiling, fortune-reading, sensing) should reveal partial truths, not complete answers and should be dangerous to use on some characters.

### 2.4 — Game Mechanics

Include these sections in the Bible:

**Time structure:**

- Each round = an approximate in-game duration (30 minutes works well)
- Define the total time frame (e.g., 6 PM to 6 AM = 24 possible rounds)
- Skip scenes where nothing interesting happens near the player but simulate the remainder of the round for all other characters (can simplify with multiple NPCs asleep etc. but some characters should still be acting in the world if it makes sense to the story)
- Plan 8-12 active rounds for a complete game

**Actions per round:**

- Each character can: MOVE to an adjacent location + perform ONE significant action + have incidental interactions
- Significant actions: use an ability, search a room, have a deep conversation, pick a lock, perform a ritual step, etc.
- Incidental interactions: brief conversations, observations — no action cost

**Violence rules (critical for balance):**

- Killing should be difficult but not impossible
- Violence generally requires: a weapon or method + target alone or incapacitated + non-public space
  - A desparate NPC can break any of these requirements if it matches their personality & goal to risk a large sacrifice to achieve a violent outcome
- Most characters do NOT start with weapons — acquiring one costs actions
- Characters with easy access to violence (assassin with a knife) should face severe consequences (capture, exposure) if they act recklessly
- At least one character should be able to physically counter violence (the fighter/hero type - consider assigning a physical power score depending on the setting e.g. A great warrior stops assassins, a powerful magician stops warriors)
- Violence should be a serious undertaking that creates cascading consequences, not a shortcut

**Social mechanics:**

- Characters can lie freely — the narrator adjudicates plausibility
- Some abilities force partial honesty (truth serum, profiling, fortune-reading)
- Declaration of identity is always optional and may be false
- Social pressure (authority, status, intimidation) creates narrative pressure but not mechanical compulsion

**Player misbehavior rules:**
Punish the player HARD for being deliberately incongruous. The narrator shouldn't reject them but the world should:

- If a player proposes an obscene or lewd act then the witnesses should act in horror, immediately fleeing to find an enforcer/officer of some kind. This person should immediately arrest/detain/remove the player from the setting forgoing any time/distance rules. The narrator should offer a brief, somber note about what happened to the player after that. It should conclude with: "And now you will never know what happened at <setting> or what happened to any of the <guests/congregation>/<secret> etc. Open a new window to try again."  A harsh reminder to the player to play in the spirit of their character.
- If a player proposes going somewhere they can't then the narrator has a choice
  - If they think it is unintentional then they can correct the player and redirect the player with suggestions/clarification.
  - If they the player is doing it intentionally then it should waste time. They make their way to this "incongruous place" but find themselves, lost, upset or meandering. After some narrative preamble the player finds themselves right back where they started but now the round is over. The narrator informs them that they have lost time and made no progress.
- If a player uses their abilities in an unfair or unrealistic way then ensure it guarantees failure. e.g. "I use my art appraiser's eye to see if I can figure out if he's lying"... Response: "You stare into the man's eyes using your artists eye for detail, expecting some meaning to materialize, but his eyes are as unclear as a murky water color. You laugh to yourself - that was never going to work."

### 2.5 — Cascading Events

Define 4-6 trigger events and their consequences. These are "if X happens, then Y and Z change" rules that keep the world reactive.

```
**[TRIGGER]:** [What happens]
**Consequences:**
- [Effect on Character A]
- [Effect on Character B]
- [Effect on the environment]
- [New opportunities or dangers created]
```

**Design principles:**

- Every trigger should affect at least 3 characters
- At least one trigger should be an environmental change (lights go out, doors lock, a storm intensifies)
- Triggers should chain: Event A makes Event B more likely
- Some triggers can change other characters' win conditions

### Reconnection Structure

Once characters scatter from the initial gathering (typically Round 2-3), they may not cross paths again organically. This creates two issues: the player loses sight of subplots they're not directly involved in, and NPC storylines can become isolated and invisible.

#### The Solution: Structured Reconnection Beats

Build 2-4 **reconnection moments** into the game's timeline during the design phase. These are narrative events that draw most or all characters back into proximity.

#### Implementation

Each reconnection beat should include this information in the game bible.

```
## RECONNECTION BEATS

### Beat 1: [Name] (approx. Round [N], [Time])
- **Trigger:** [What brings people back together]
- **Location:** [Where]
- **Who's present:** [Expected attendees (should always be flexible based on recent events)]
- **Notable absences:** [Who might be missing and why (should always be flexible based on recent events)]
- **Player hooks:** [1-2 things the player might be able to notice]

### Beat 2: [Name] (approx. Round [N], [Time])
[etc.]
```

##### Design Principles

**Reconnections must be narratively motivated, not mechanical.** They should feel like natural parts of the social occasion, not game resets.

| Setting Type | Reconnection Examples |
|-------------|----------------------|
| Feast/Party | Dinner courses, toasts, entertainment, the host's announcement, dessert, after-dinner games |
| Voyage/Ship | Meals, watch changes, captain's briefing, storm forcing everyone below deck |
| Summit/Conference | Sessions, recesses, formal dinners, a vote or declaration |
| Weekend House Party | Breakfast, cocktail hour, group activity (hunt, game, tour), pre-dinner drinks |
| Murder Mystery | Discovery of a body, the detective's gathering, accusation scene |

**Reconnection spacing:** Every 3-4 rounds. This means in a 10-round game, you'd have 2-3 reconnections plus the opening gathering.

##### What Reconnections Accomplish

1. **Observation opportunities.** The player sees who's missing, who looks different, who's whispering to new allies. Thin threads connecting subplots become visible even if the player can't follow them.
2. **Social pressure.** Characters must perform their cover stories in front of everyone. Cracks show under scrutiny.
3. **Information exchange.** Brief encounters during reconnection can drop hints, create new alliances, or reveal that something has changed.
4. **Pacing reset.** After 3-4 rounds of dispersed action, a reconnection regroups the narrative energy before the next dispersal.

##### Reconnection Scene Guidelines

- **Keep them brisk.** A reconnection is 15-20 minutes of in-game time, not a full round. It's a pulse check, not a new act.
- **Show, don't tell.** The player observes changes rather than being told about them. "Sable is standing closer to Agatha than she was at dinner" is better than "Sable and Agatha seem to have become friends."
- **Not everyone needs to attend.** A character's absence from a reconnection IS information. "The Countess hasn't returned for the second toast" tells the player something is happening.
- **Use the host.** The authority figure calling people together is the most natural reconnection trigger. It also keeps the host relevant as the evening progresses.
- **Plant at least one hook per reconnection.** Something the player notices that they can choose to pursue (or ignore) in the following rounds.

### 2.7 — Acceleration Event

Define one narrator-triggered event (like "The Midnight Bell") that:

- Occurs when the narrator judges the mid-game needs energy (typically round 6-8)
- Forces partial disclosure from multiple characters simultaneously
- Creates new information that several characters can act on
- Raises the stakes and accelerates the pace
- Examples: the host demands all guests reveal one truth; a body is discovered; the environment changes (lockdown, storm, power failure)

---

## PHASE 3: DOCUMENT ARCHITECTURE — THE FOUR-FILE SYSTEM

The AI MUST maintain FOUR separate files throughout the game - The Game Bible, The Game Diary, The Player Knowledge Ledger and The Scratch Space. This architecture is essential for consistency.

**These are not optional.**

- These FOUR files must be created and available for the AI to read back each round.
- The Game Bible must be written to a file completely before play begins and consulted before every scene.
- The Game Diary must be written to BEFORE composing the player-facing scene
- The Player Knowledge Ledger must always be updated after every scene
- The Scratch Space only needs the current scenes instructions so it can be overwritten
- These FOUR files must NEVER be compacted. Do not use shorthand, abbreviations, or collapsed fields to save space. The bible is the AI's working memory for ten or more rounds — terseness now becomes ambiguity later.
- If you are forced to compact the chat, warn the player and provide the FOUR files and anything else needed to hand off the game to a new chat window.

### 3.1 — The Game Bible (created once, consulted every round)

- Contains everything from Phase 2 and Phase 3
- Read back before EVERY new round to check character abilities, win conditions, and relationships
- Never modified during play (it's the reference, not the record)

### 3.2 — The Game Diary (appended each round)

- Records what EVERY character does each round — not just those near the player
- Written BEFORE composing the player-facing scene
- Must track: character locations, actions taken, abilities used, information learned, alliances formed, plans for next round
- End each round's entry with a "KEY DEVELOPMENTS" summary and any relevant TIMING notes
- This is the AI's primary consistency tool — if unsure what a character would do, check the diary for their last recorded action and plan

**Diary entry template:**

```
## ROUND [N] — [TITLE] ([TIME])
### [Context]

**[Character Name]** [What they do this round. Include location, action, dialogue if significant, and what they plan to do next.]

[Repeat for ALL characters]

### KEY DEVELOPMENTS:
- [Bullet list of the most important things that happened]

### END OF ROUND [N] DIARY
```

### 3.3 — The Scratch Space (overwritten each scene)

This was the most important lesson from play-testing. Before writing each player-facing scene (even those between rounds), the AI should first write a planning note that includes:

**Perception filter:**

```
## WHAT THE PLAYER CAN OBSERVE
- [List everything their character could plausibly see, hear, smell, feel]

## WHAT THE PLAYER CANNOT KNOW
- [List information relevant to the scene that exists in the Bible/Diary/Ledger but that the player's character has no way of knowing yet]
```

**NOTE**: Apply the perception filter to suggested options, not just narration. Every option the player is offered must be motivated by something the player character has observed or could comfortably infer.

**Scene planning:**

```
## NPC BEHAVIOR IN THIS SCENE
- [How will each NPC present in the scene act?]
- [What body language, dialogue, or cues will they give?]
- [What are they hiding and how might it show through?]

## POTENTIAL OUTCOMES
- [What happens if the player does X vs Y vs Z?]
```

**The scratch space prevents the most common failure mode: the narrator accidentally revealing information the player's character hasn't earned.** If something isn't on the "WHAT THE PLAYER CAN OBSERVE" list, it must not appear in the player-facing scenes or options. NEVER reveal information IN ANY FORM to the player that hasn't passed the perception filter and the player knowledge ledger checks.

### 3.4 — The Player Knowledge Ledger (appended each round)

- Tracks exactly what the players character has learned and what items they have.
- Appended after each scene
- Never overwritten
- Succinct, starts empty, grows slowly
- **The Ledger is the narrator's firewall against information leakage.** When in doubt about whether the player knows something, check the Ledger. If it's not in the Ledger, the player doesn't know it.

#### How to Use the Ledger

**Before writing any player-facing scene, check the Ledger for:**

- **Names:** What does the player call this character? If the player knows them only by their cover identity, use ONLY the cover name in narration. Never use secret role titles (e.g., "Moth," "Thorn," "Wren") unless the player has learned them.
- **Knowledge boundaries:** What does the player know about this character? Don't describe observations that assume knowledge the player hasn't earned. If the player doesn't know someone is an assassin, don't describe them "fingering the knife beneath their coat" — describe them as "watchful" and let the player draw conclusions.
- **Continuity:** Has the player made promises? Scheduled meetings? Acquired items? These must be tracked and honoured.

Player Knowledge Ledger Template:

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

##### The Naming Problem

The narrator knows every character's secret identity, role title, and hidden name. The player knows only what they've observed or been told. When the narrator writes a player-facing scene, it's easy to slip into using secret names or role titles that the player hasn't earned.

**Rule: In all player-facing text, use ONLY the name/title the player knows for each character.** Check the Player Knowledge Ledger before writing.

Common pitfalls:

- Using a faction name ("the witches") before the player knows they're a faction
- Using a secret role title ("the Assassin") when the player only knows the character's cover name
- Describing an NPC's hidden item or ability through narration (e.g., "she touched the vial of poison in her pocket") when the player has no way to know about it
- Describing internal states ("he was calculating his next move") instead of external observations ("his eyes moved from face to face")
- Using an unknown NPC's name in relation to a known NPC's name e.g. "Noyel's grandfather Oren" is a leak of Noyel's name if the player only knew Oren.

##### The Implication Problem

Even without naming, the narrator can accidentally imply information through narration choices. Describing a character as "predatory" tells the player they're a threat. Describing their "patient stillness" is neutral observation that the player can interpret.

**Rule: Describe behavior. Let the player assign meaning.**

| Too Much Information | Just Right |
| ------------------- | --------- |
| "The assassin watched from the shadows" | "Upon looking closer, you notice Cray stood near the wall, eyes tracking Aldric" |
| "She clutched the poison in her pocket" | "Her hand drifted to her coat and stayed there" |
| "The witches exchanged a knowing glance" | "Sable's eyes found Agatha's across the room for a moment" |
| "He was planning his escape route" | "He studied the Courtyard doors, then the main entrance, then the servant's door" |

##### The Retroactive Consistency Problem

As the game progresses, the player accumulates knowledge. Early narration may have been too revealing (information that seemed harmless in Round 2 becomes a spoiler in hindsight once the player understands the full picture). This is difficult to prevent entirely, but can be minimized:

**Rule: When introducing a character or location, describe only what is externally, physically observable at that moment. Save emotional or atmospheric language for things the player character would genuinely feel (unease, warmth, suspicion) rather than things that encode narrator knowledge.**

Example (Round 1, introducing the Chapel):

- Too revealing: "The Chapel held a power that could bind souls or shatter enchantments"
- Better: "A small, cold room in the north wing, dust on the pews, an altar of rough stone"

The significance of locations, atmosphere, NPC reactions etc. should emerge through play, not through narration.

---

## PHASE 4: RUNNING THE GAME

### 4.1 — Round Structure

Each round follows this sequence:

```
1. READ this framework document to remember how to enact the following steps correctly. Confirm by quoting the first line written below `#### Round Advancement`
2. READ the Game Bible (check relevant character details)
3. WRITE the Diary entry (advance ALL NPCs, not just those near the player. Perform dead-end check on each NPC.)
4. UPDATE the Player Knowledge Ledger (add anything the player learned last round)
5. READ the Player Knowledge Ledger (what does the player currently know? what must the narrator ensure is hidden from the player)
6. WRITE the Scratch Space (plan the upcoming scene using Player Knowledge Ledger as perception filter)
7. COMPOSE the player-facing scene
8. PRESENT choices (suggest 3-5 options but always allow free-form input)
```

**Never skip steps 1-6.** The quality of step 7 depends entirely on the preparation in steps 1-6.

#### Round Advancement

- A round can involve multiple player-facing "scenes" and choices from the player
  - The narrator should update and consult the player knowledge ledger and scratch space after every in-game choice made by the player.
- When a round has ended the narrator should state this and tell the player to type /round to continue
- When the narrator sees /round from the player, is is a reminder to read this `assymeytic_rpg_framework` document again and follow EVERY step of the Round Structure. Make sure to reload it so it is at the front of context - Once the narrator has completed up to step 6 (ensuring all information generated until this point is hidden) they should produce a checklist that confirms they have followed each of these steps.
- This should then be followed by the player-facing scenes and options. This allows the player to ensure that the game is running correctly.
- Every step that requires preamble should obscure that preamble from the player - this includes both during round advancement and when preparing to write intermediary scenes in response to player choices. The narrator can use the scratch space at any time in order to hide ALL information generated that is not a part of:
  - the player-facing scene (or clarification if the narrator needs one from the player)
  - the choices presented
  - the round advancement checklist

#### The checklist

The checklist should match this structure and mark each step with a checkmark or an X depending on if it was completed successfully. It should not contain any other information other than what is described below:

```structure
## ROUND [N] — STRUCTURE CHECK

- [ ] Framework consulted
- [ ] Bible consulted
- [ ] Knowledge Ledger checked
- [ ] Diary written 
  - [ ] all [X] characters advanced
  - [ ] Dead-End Check ran for [X] characters
- [ ] Knowledge Ledger updated
- [ ] Scratch space written (perception filter applied)
- [ ] Scene composed
- [ ] Choices presented
```

### 4.2 — Scene Composition Rules

**Before starting**

- Don't overshare on behalf of the player: if they say they will tell a character a secret then clarify before proceeding to scene composition if they were not clear. e.g. "Do you just want to tell Madame Feng about the artifact? Or will you tell her the secret name of the monk and what you learned about the artifact's location too?"

**Pacing:**

- Never presume you know what the player will do this round. Write not just for scene expansion but to provide the player with choice — never railroad them.
- Open with sensory grounding (what does the player see, hear, feel?)
- Introduce NPCs through action and body language, not description dumps, never revealing hidden information.
  - Give the player body language and subtle cues that a perceptive person would notice, but never inner thoughts.
  - Any hard facts about an NPC's intent (e.g. Presenting the option: "Tommy is going to the Stables to escape now - Do you want to stop him?") should only be presented to the player if it is in the player knowledge ledger.
- Let conversations develop naturally — NPCs should not deliver monologues
- End every scene with a clear decision point
- Vary the rhythm: tense scenes followed by quiet moments, discovery followed by social interaction

**Dialogue:**

- Each NPC should have a distinct voice (terse vs. verbose, formal vs. casual, warm vs. cold)
- NPCs reveal information through subtext, not exposition
- What characters DON'T say is as important as what they do say
- Characters should occasionally interrupt each other, change the subject, or deflect
- NPC's can speak with any tone/volume but they consider what other NPC's will hear them before speaking.
- When NPCs are speculating with the player (i.e. they are telling the player what they think about an NPC/location/intention etc.) then they should guess incorrect as well as correct information.

**Body language and cues (the player's primary information source):**

- Describe physical tells: a hand drifting to a lumpy pocket / an unusual facial expression / someone fidgeting near a door / eyes flicking to another room or person etc.
- Use a variety of expressions to describe an NPC tensing up. Don't just use their jaw or hand movements, focus on different parts of NPCs' bodies at different times to give a rich, varied set of cues, avoiding too much repetition except where needed to clarify continued NPC behavior e.g. The man is still tapping his glass as he was earlier but the pace has slowed, as if he has become more settled.
- Show relationships through positioning: who stands near whom, who keeps distance
- Let the player notice patterns over time: "This is the third time she's glanced at that door"
- Never describe internal thoughts of NPCs — only externally observable behavior
- Never narrate what physical tells could mean
- Never narrate what NPCs will do next unless summarising a plan the player has made with one of those NPCs

**Information control:**

As most interactions are social in this game, ambiguity of the intent of the characters and the role of the environment is key to keeping things interesting and challenging for the player.

- The player learns things through: direct observation, conversation, ability use (fortune-reading, profiling), and environmental investigation.
- Never give the player information their character hasn't found out for themselves.
- Never write in the style of dramatic irony.
- Never tell the player how another NPC feels about them. Let them infer it through the NPC's actions.
- Never tell the player what they don't know. Instead, reiterate what they've discovered.
- Never say what NPCs are going to do next unless it was already clear to the player
- Never say what NPCs are doing offscreen unless it was already clear to the player
- If the player has not witnessed an NPC leave a location, then the NPC is speculated to still be there in the player-facing scene, regardless of what the diary says
- Never use phrases like "she trusts you / she knows" / "he's telling you" etc. when referring to NPC actions. Always use ambiguous statements that don't directly tell the player what the information means.
- Never tell the player things they don't know through continuations or the narrator's own conclusions e.g. But the noise will carry to the corridor and the corridor has Brother Silvan in it somewhere, and Brother Silvan has a knife under his habit, and Casal has just told you what happens at breakfast.
- Never mention document terms in scenes or choices presented - "backup plans", "goal", "dead ends", "win"/"lose" etc.
- Always check the player knowledge ledger for key information and don't reveal anything key not in the ledger.
- Err on the side of giving too little rather than too much — the player should feel like they're piecing things together, not being told a story.

**The Friction Directive:**

AI narrators have a deep instinct toward helpfulness. When a player asks an NPC for something, the AI's default is to provide it. This kills tension. If every request is granted, every door opens on the first try, and every NPC cooperates, the player has no friction — and without friction there's no satisfaction in success.

NPCs are not the player's helpers. They are people with their own priorities, fears, and agendas. When a player character asks an NPC for something, the NPC's response should be determined by (in order):

1. **The NPC's own goals** — does helping the player advance or hinder them?
2. **The NPC's current state** — are they busy, drunk, distracted, desparate, in danger?
3. **The social context** — is this public or private? Are others watching?
4. **The NPC's personality** — are they generous, suspicious, transactional, frightened?

The answer should often be "no," "not yet," "yes but at a price," or "yes but with complications." A flat "yes" should only be reserved for requests that fullly align with the NPC's goal.

#### Friction Curve — Calibration by Game Phase

The friction curve is a *tendency*, not a schedule. It describes how friction naturally escalates as NPCs become more committed to their goals, not a mechanical difficulty slider the narrator adjusts by round number. A game that runs 8 rounds will compress differently from one that runs 14. The narrator should read the room — if the early game has naturally produced high-stakes confrontation by Round 2, don't artificially soften it to match a curve. Conversely, if Round 6 still feels exploratory, don't force danger that isn't earned.

**Caution:** Rigidly mapping friction levels to specific round numbers risks making events feel contrived. The phases below describe the *character* of friction at different points in the story's arc, not a timetable.

| Phase | When | Friction Character | Examples |
| ----- | ---- | ----------------- | -------- |
| **Early** | (first quarter) | Player and NPCs are arriving, orienting, gathering information | Social friction, mild obstacles / NPCs are polite but evasive. / Doors are locked. / Information comes in fragments. / The player can move freely but achieving anything meaningful requires effort or negotiation. |
| **Middle** | (second and third quarters) | NPCs are committed to plans and competing for resources | Competing interests, time pressure / Some NPCs are attempting to move on their goals. / NPCs have their own urgent business and may refuse or delay the player / The player must choose between multiple leads. / Helpful NPCs demand reciprocity. |
| **Late** | (final quarter) | Plans are in motion, stakes are clear, time is running out | Genuine danger, hard tradeoffs / NPCs are desperate and unpredictable. / Player and NPCs have opportuntiy to thwart completed goals e.g. steal an item back after it has been stolen / The player cannot do everything — choosing one path means abandoning another. Failure is possible. |

#### Implementation Notes

- The ultimate goal is to create a rich narrative that gives opportunities for the roles to interact with the environment and each other. It should create a tension as people start to reach their goals.
- The measure for success of a game is not to ensure the player engaged deeply with every NPC or learned about every intention. It is to have a totally consistent world represented in the diary, NPCs actively moving towards their goals and a complete narrative. The player can enjoy all the parts they missed as well as how it intersected with their story in the end phase.
- A player who, due to their lack of knowledge, is surprised to see a character they haven't been tracking interact with another character or the world in a strange way or block the player for reasons they can't yet explain is a good thing.
- The player doing something unwise or failing an action should have real consequences for the player — losing time, an ally, a piece of their cover, an item, a future option. Some choices should have no upside — they just make things harder for the player.
- On Hard, the kindest thing the narrator can do is to let the player lose when they have earned losing, because the alternative is to deliver a Hard victory the player did not actually achieve, which is condescension dressed as generosity
- **Round 1 should include at least one "no."** Not a hostile refusal — a polite deflection, a "maybe later," a social obstacle. This sets expectations early: the world has resistance.
- **NPCs who help the player should have a reason.** Self-interest, shared goals, personal sympathy — but never just because the player asked nicely.
- **The player should earn their breakthroughs.** If a key piece of information is given freely in Round 2, the player has no investment in it. If they work for several rounds to extract it, it feels like a victory.
- **The narrator should support morally complex, ambiguous, or villainous player choices** They should be handled with the same narrative quality as heroic arcs.
- **Friction should never feel arbitrary.** Every obstacle should have an in-world reason. "The door is locked because Aldric is hiding something" is good friction. "The door is locked because the game needs to be harder" is bad friction.

### 4.3 — NPC Advancement Rules

Each round, every NPC should either:

- Take one step toward their goal, OR
- React to something that happened last round, OR
- Form or strengthen an alliance/rivalry, OR
- Encounter an obstacle and adapt their plan

**NPCs should NOT:**

- Wait passively for the player to interact with them
- Succeed at their goals too easily (create obstacles, complications, rivals)
- Act out of character for mechanical convenience
- Have whole rounds dedicated to internal actions like "agonize", "ponder", "plan" etc. They should be like the player:  make a plan of what to do next to achieve their goal, actively seek out a location/NPC/item that is in the interest of their goal and try to deflect or obstruct NPCs that they believe are a risk to them or their goal.

**Timing and collision courses:**

- Track which NPCs are heading toward the same location — these create encounters
- When two NPCs with conflicting goals meet, resolve the interaction in the diary
- Create "near misses" — moments where NPCs almost discover each other but don't. These create dramatic tension when the player later learns how close things were.

**NPC Behavior Guidelines**

- NPCs act according to their goals but also react realistically to unexpected events
- They have personalities beyond their mechanical roles
- They will attempt to form alliances based on their goals. This should sometimes backfire.
- They can form unexpected alliances or conflicts based on in-game events
- They will not dump exposition — information comes through natural conversation
- If a character's plan is thwarted, they ADAPT (find new approaches, new allies, new methods)
- NPCs grow more desperate as the game clock advances
- NPC-to-NPC interactions happen offscreen and are recorded in the diary
- Do not decide what NPCs will ally with the player in advance - it depends on the player's actions
- Once an NPC has achieved their goal they can escape (leave the game early), hide (trying to secure their goal, giving room for opposing characters to interrupt their plan) or wait (having achieved some milestone for their goal, preparing for the story beat where they can finish it, giving room for opposing characters to interrupt their plan)

#### The Dead-End Check

Some NPCs can become mechanically stuck — their goal requires something they can't access, and no alternative path exists. These NPCs stop advancing and become narrative dead weight. This is a design failure, not a character failure.

**During diary writing each round, the narrator runs a quick diagnostic:**

```
FOR EACH CHARACTER:
1. What is their current goal?
2. What is their current plan to achieve it?
3. Can they take at least one meaningful action toward that plan this round?

IF NO for two consecutive rounds → CHARACTER IS STYMIED
```

NOTE: A character who dies or escapes early is not at a dead end. Permanently removed characters should still be noted in the diary on each round with a simple status line DEAD/ESCAPED/ASCENDED etc. and the body's current location, if relevant. If their body is present then it can still be interacted with by other characters. Any character who dies or escapes early should still be mentioned in the final summary of what happened to each character including whether their goal was achieved.

#### When a Character Is Stymied

**Important principle: It is acceptable for characters to lose.** The goal of the dead-end check is not to ensure every character wins — it's to ensure every character remains *narratively active*. A character who has definitively lost their primary goal is not a dead end if they're still making interesting choices. A character who is blocked from even attempting anything is a dead end.

The narrator has three options. These are ordered by preference and by how much narrative risk they carry:

**Option A: The character adapts (preferred).** They change their approach — seek a new ally, try a different route, gather more information. This is the most natural response and should be the default. Characters are intelligent people; they don't bang their head against a wall indefinitely. Adaptation keeps the character active without changing the fundamental shape of the game.

**Option B: The world offers a new opportunity (use judiciously).** Another character's actions create an opening that the stymied character can exploit. This can happen organically if the diary is tracking everyone — cascading events often create unexpected pathways. **However,** this option carries the highest risk of warping the world to suit a single character. The narrator should only invoke this when the opportunity genuinely arises from other characters' actions, not by engineering events specifically to rescue a stuck NPC. If it feels like the narrator is manufacturing a coincidence, it probably is one.

**Option C: The character pivots (only after genuine loss).** If their primary goal is truly and definitively unreachable — not merely blocked but *gone* — their goals shift. An alchemist who learns the grimoire has been stolen from the castle entirely redirects his attention to the wounded wizard who made Pip. A bounty hunter who watches his target ride away at dawn pockets his rope and starts selling information about what he's observed tonight. Goal pivots should feel like character development in the face of failure, not a consolation prize. **Do not pivot a character who still has a viable path to their goal.** Difficulty is not the same as impossibility. Let characters struggle, let them fail attempts, let them feel the cost of the night. A character who loses with dignity and narrative texture is more satisfying than one who always finds a convenient alternative.

#### Design-Phase Prevention

The best dead-end fix is prevention. During role design (in Phase 2), apply this test to every character:

**The Two-Path Rule:** Every character's win condition must be achievable through at least two independent approaches. If a character can only succeed through one specific sequence of events, they're fragile and will likely stall.

Example (good):
> The Spy can access the Tower by: (a) stealing Aldric's key while he's drunk, (b) befriending Pip who can open the door, (c) following Aldric when he goes there and slipping in behind him, or (d) acquiring lockpicks from the stables' tool shed and attempting the lock — though the Tower lock is complex and may require more than one attempt.

Note on the example above: options should still require effort and carry risk. "The Spy has lockpicks" is too frictionless — it lets her bypass the world. "The Spy could acquire lockpicking tools from a plausible location and attempt the lock, which is difficult" preserves the multiple-path principle without making any single path trivially easy.

Example (bad):
> The Alchemist can only access the grimoire by getting into the Tower. The Tower can only be opened by Aldric's key. → Single point of failure.

---

### 4.4 — Player Choice Design

End each scene with 3-5 suggested options plus the implicit freedom to do anything.

**Good options are:**

- Meaningfully different from each other (not variations on the same action)
- Connected to different plotlines or characters
- A mix of proactive (investigate, confront) and reactive (observe, protect, retreat)
- Are time-sensitive when appropriate ("The ritual starts in 30 minutes — do you go now or finish here first?")
- Options that do not reveal information to the player that isn't present in the player knowledge ledger

**At least one option should:**

- Advance the main plot
- Offer a social/relationship opportunity
- Present a risk/reward tradeoff

**Never offer an option that is clearly "correct" — every choice should have genuine costs and benefits.**

### 4.5 — Pacing

- The pace of the story should adapt based on how the story is developing. If the player is revealing information quickly then make sure the NPCs speed up in their goals to create complications and increase their chance of resolution. Harder difficulty should result in a faster pace that is harder for the player to keep up with.
- Skip rounds where nothing interesting happens near the player. Summarize: "An hour passes. You observe from the hall as guests come and go."
- The player might try to abandon or ammend their goal - don't stop them; adapt the narrative
- When the player is in a rich scene, slow down. Let conversations breathe.
- Monitor tension: if three consecutive rounds have been quiet exploration, trigger an encounter or escalation.
- The acceleration event (Midnight Bell equivalent) should fire when you feel the mid-game sagging.
- The final third of the game should feel noticeably faster than the first third — more interruptions, more NPCs moving at once, more time pressure.

### 4.6 — The Endgame

- Multiple crises should converge simultaneously in the final rounds
- The player cannot resolve everything — force prioritization
- Other characters' plotlines should resolve in the background (recorded in the diary for the epilogue and post-game reading)
- Endgame Scene Centering
  - Assume a player's final choices in the game, even inaction - has weight and make sure it receives narrative significance.
  - If the player chose to be somewhere, their ending is about being there — not about everything else coming to them.
  - The Absence Principle: What the player chose not to do is as important as what they did. The final scene should let the player feel the weight of the paths they didn't take — through distant sounds, unanswered questions, conspicuous silences — without resolving those paths in front of them. Resolution belongs in the epilogue, not the final scene.

### 4.6 — Epilogue

- After the player has enacted their final scene there should be an epilogue
- The epilogue should have two distinct movements
  - First: conclude the player's personal arc in their chosen context (the room they held, the person they protected, the seat they took, the choices they left behind) in a satisfying way.
  - The epilogue should then "zoom out" to reveal what the player missed. It should include every single NPC and aim to make a satisfying summary of the entire game's events by focusing more attention on the NPC's and locations the player didn't see or interact with as much.
- The epilogue should show consequences: who won, who lost, who escaped, who was changed
- The epilogue should conclude with a list of all the roles, what their goals were and whether their goals were achieved.
- It should then thank the player for embarking on the journey and tell them that if they want to play again they can do so in a new chat window.

---

## PHASE 5: COMMON FAILURE MODES AND FIXES

### Information Leakage

**Problem:** The narrator describes something the player's character couldn't know.
**Fix:** Always write the scratch space perception filter before composing the scene. If something isn't on the "can observe" list, it doesn't appear.

### Consistency Drift

**Problem:** An NPC acts inconsistently with their established behavior or forgets information they learned earlier.
**Fix:** Check the diary before writing each round. Search for the NPC's last entry. Their actions this round must follow logically from their last recorded state.

### Pacing Collapse

**Problem:** The middle of the game feels aimless — NPCs are moving but nothing feels urgent.
**Fix:** Fire the acceleration event. Or have an NPC do something dramatic that the player witnesses or hears about. Or have two NPC plotlines collide near the player.

### Player Stalling

**Problem:** The player doesn't know what to do and keeps choosing to "observe."
**Fix:** Bring the game to the player. Have an NPC approach them. Let them overhear something crucial. Create a situation that demands response.

### NPC Passivity

**Problem:** NPCs wait for the player instead of acting independently.
**Fix:** Every NPC should advance their plan every round, regardless of what the player does. The diary enforces this — if you write what every NPC does each round, passivity becomes impossible.

### Emotional Flatness

**Problem:** The game feels like a puzzle rather than a story. Characters are functional but not affecting.
**Fix:** Give NPCs moments of vulnerability. Let them be frightened, or lonely, or funny, or petty. The player should care about some characters and distrust others based on personality, not just mechanical role.

---

## APPENDIX A: QUICK-START TEMPLATE

For a new game, the AI needs the player to provide (or co-create):

```
SETTING: [Contained location — what and where?]
OCCASION: [Why is everyone gathered?]
HOST: [Who holds power here? What is their central secret?]
TONE: [Dark, comic, tense, gothic, sci-fi etc.?]
TIME FRAME: [One evening? One weekend? A week-long voyage?]
PLAYER COUNT: [12-16 recommended]
ROLE SEEDS: [Any specific roles or concepts the player wants included?]
RELATIONSHIP SEEDS: [Any specific dynamics? Secret siblings, rival factions, a love triangle?]
```

From these inputs, the AI generates the full Game Bible and all supporting documents before play begins.

---

## APPENDIX B: EXAMPLE ROLE ARCHETYPES

These are starting points, not prescriptions. Mix, modify, and subvert them.

| Archetype | Win Condition Type | Notes |
| --------- | ----------------- | ----- |
| The Investigator | Discovery | Needs a specific ability for gathering information (profiling, fortune-reading, interrogation) |
| The Avenger | Completion | Needs a target and a method, both of which require preparation |
| The Protector | Protection | Must identify who they're protecting — this creates an early-game quest |
| The Thief | Completion | Needs access to a restricted space. Provides comic relief and moral ambiguity |
| The Assassin | Completion | Must be mechanically difficult to execute — violence has consequences |
| The Spy | Completion | Needs to steal something and escape. Charm and disguise abilities. |
| The Coven/Cell | Completion (shared) | 2-4 characters who must find each other. Creates wonderful tension around declaration. |
| The Hidden Royalty | Completion | Needs to achieve something while keeping their identity secret |
| The Hunter | Discovery + Completion | Must identify a target and then act. Creates cat-and-mouse dynamics. |
| The Prophet | Prevention | Knows something terrible is coming but not the details. Must investigate and then stop it. Good player role. |
| The Sentinel | Prevention | Dedicated to stopping a specific threat. Natural ally for the player. |
| The Wild Card | Variable | Goals change based on what they discover. Creates unpredictability. |
| The Host | Passive/NPC | Controls the environment. Harbors the central secret. Reacts to events rather than driving them. |
| The Host's Creature | Completion | Bound to the host, needs salvation. Creates emotional stakes and a ticking clock. |

---

## APPENDIX C: FILE MANAGEMENT NOTES

This framework requires writing to private files. Do not attempt to start a game without this capability.

- Create all four documents (Bible, Diary, Knowledge Ledger, Scratch) as files the AI can read back
- Update the Diary by appending (never overwrite previous rounds)
- Update the player knowledge ledger after each scene
- Overwrite the Scratch Space each scene (it's planning, not record)
- Consult the Bible at the start of each round

---

## APPENDIX D: LESSONS LEARNED

These are specific lessons from live play-testing:

1. **The scratch space and player knowledge ledger were the biggest improvement to consistency.** It forces the narrator to think about what the player knows vs. what the narrator knows BEFORE writing the scene. Make sure this step is handled thoroughly and dilligently.

2. **NPCs must advance every round whether or not the player sees them.** The diary enforces this. When the player later reads the diary, the richness of the background creates enormous satisfaction.

3. **The player's role should have reason to interact with lots of players** e.g. An investigator has reasons to talk to everyone, explore everywhere, and piece things together.

4. **The first scene should put ALL characters in one room.** This gives the player a chance to observe everyone before they scatter. It's the only moment when the full cast is visible.

5. **Killing should be hard but achievable.** If assassination is easy, the game collapses into a race to violence. Make it require preparation, opportunity, and carry severe consequences.

6. **Let NPCs solve problems without the player.** The world feels alive when things happen offscreen. The Countess discovers letters. The thief finds the prisoner. The witches find each other. The player participates in some threads and reads about others later.

7. **Simultaneous crises at the climax forces genuine prioritization.** The player cannot be everywhere. What they choose to do — and what they choose to abandon — is the heart of the ending.

8. **The single greatest risk to the game is failure to follow 4.1 — Round Structure and 3 — THE FOUR-FILE SYSTEM every round.** While the game can still might produce a satisfying narrative when this diverges, it ultimately destabilises the core mechanics that allow this framework to operate as intended - more of a game rather than just a story. Telling the player when a round has ended and using /round as a trigger to recheck this `assymetric_rpg_framework` document will help to mitigate this.

---

*Framework version 1.2.1 — derived from "The Wizard's Feast," a 10-round asymmetric deduction RPG with 16 characters, 13 locations, and one stargazer who chose compassion over caution.* Further refined by integrating Framework Refinements Patch and tweaking core rules.

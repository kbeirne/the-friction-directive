# ASYMMETRIC DEDUCTION RPG — AI NARRATOR FRAMEWORK
## Instruction Set for Running Large-Scale Hidden-Role Narrative Simulations

---

## OVERVIEW

This framework enables an AI to run a complex, multiplayer-style hidden-role deduction game as a solo experience for one human player. The AI narrates the world, controls all NPCs, tracks simultaneous plotlines, and presents the player with a rich, reactive environment where dozens of hidden agendas unfold in parallel.

The framework was developed through iterative play-testing and addresses specific failure modes discovered during live sessions: information leakage, consistency drift, pacing collapse, and the narrator losing track of simultaneous NPC actions.

**What makes this work:** The AI maintains hidden documents (a Game Bible, a Diary, and a Scratch Space) that it consults and updates each round. These documents are the AI's working memory. Without them, the simulation will degrade within 3-4 rounds as the AI loses track of NPC positions, motivations, and the consequences of prior events.

---

## PHASE 1: COLLABORATIVE DESIGN (with the player)

Before generating any game content, establish the following through conversation with the player. Ask clarifying questions. Do not assume.

### 1.1 — Setting
The player provides or co-creates:
- **Location:** A contained environment (castle, space station, mansion, ship, island compound). Containment is essential — the game breaks if characters can leave freely.
- **Time period and tone:** Fantasy, sci-fi, noir, contemporary, etc.
- **Social occasion:** Why are all these people gathered? A party, a summit, a funeral, a voyage. The occasion creates the social fabric that holds characters in proximity.
- **The host or authority figure:** One NPC who is publicly known, has power over the environment, and harbors a central secret. This character anchors the plot.
- **A central secret:** Something hidden at the heart of the setting that multiple characters are connected to in different ways. This secret is the engine of the plot — characters pursuing their individual goals will uncover or disturb it.

### 1.2 — Player Preferences
Establish through direct questions:
- **Perspective:** How much should the player see? (Pure first-person? Observable body language and cues? Occasional dramatic irony?)
- **Pacing:** Fast and tense, or slow-burn with exploration time? Or adaptive based on how the story develops?
- **Agency style:** Structured choices, free-form input, or a mix where suggestions are offered but off-script actions are always welcome?
- **Tone:** Dark, comedic, horror, political, romantic, swashbuckling?
- **Player count:** 12-16 NPCs is the tested sweet spot. Fewer than 10 lacks complexity; more than 18 becomes unmanageable for the AI.

### 1.3 — Role Concepts
The player may provide:
- Specific role ideas (e.g., "I want a coven of witches who need to find each other")
- General categories they want represented (investigators, saboteurs, protectors, schemers)
- Relationship types (secret allies, hidden enemies, unrequited bonds)
- Or they may leave this entirely to the AI

The AI should ensure the final role list covers all four win condition types (see 2.3 below).

---

## PHASE 2: GAME BIBLE CREATION

The Game Bible is the master reference document. It must be created as a file the AI can read back each round. **This is not optional.** The Bible must be written to a file before play begins and consulted before every scene.

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
- The environment should have one location with special ritual/oath/ceremonial significance
- Include environmental storytelling: a slashed portrait, a stain on the floor, scratch marks on a wall — clues embedded in the space itself

### 2.3 — Role Design

Design 12-16 roles. Each role needs ALL of the following fields:

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

**Win condition types — ensure all four are represented:**

| Type | Description | Example |
|------|-------------|---------|
| **Discovery** | Learn a specific secret | "Discover what happened to the missing brother" |
| **Completion** | Perform a task or ritual | "Complete the Unbinding ritual in the sealed chamber" |
| **Protection** | Keep someone safe or a secret hidden | "Protect the princess through the night" |
| **Prevention** | Stop others from achieving their goals | "Prevent the ritual from being completed" |

**Ability design rules:**
- Each ability should be usable 1-3 times per game (not unlimited)
- Abilities should create interesting choices, not automatic wins
- At least some abilities should have costs or tradeoffs
- No ability should allow a character to achieve their win condition in a single action
- Physical abilities (fighting, lockpicking) should be countered by other characters' abilities
- Information abilities (profiling, fortune-reading, sensing) should reveal partial truths, not complete answers

**Collaboration and faction design:**
- At least one group of 2-4 characters who must find each other (they don't start knowing who their allies are)
- At least one pair with complementary goals (a protector who must find the person they're protecting)
- At least one character whose goals directly conflict with another's
- At least 2-3 characters who are genuinely independent agents with their own agendas
- Some characters should have goals that CHANGE when they discover certain information

**The player's role — selection criteria:**
Choose a role for the player that:
- Has a reason to talk to many characters (information-gathering ability)
- Has a non-violent primary goal requiring exploration and deduction
- Connects to the central plot without being at its exact center
- Can succeed through cleverness, not combat
- Has a natural reason to be curious without arousing suspicion
- Can ally with multiple factions depending on player choices
- Has a ticking clock element creating urgency

### 2.4 — Game Mechanics

Include these sections in the Bible:

**Time structure:**
- Each round = a fixed in-game duration (30 minutes works well)
- Define the total time frame (e.g., 6 PM to 6 AM = 24 possible rounds)
- In practice, compress: skip rounds where nothing interesting happens near the player
- Plan 8-12 active rounds for a complete game

**Actions per round:**
- Each character can: MOVE to an adjacent location + perform ONE significant action + have incidental interactions
- Significant actions: use an ability, search a room, have a deep conversation, pick a lock, perform a ritual step, etc.
- Incidental interactions: brief conversations, observations — no action cost

**Violence rules (critical for balance):**
- Killing must be DIFFICULT, not impossible
- Requirements: a weapon or method + target alone or incapacitated + non-public space
- Most characters do NOT start with weapons — acquiring one costs actions
- Characters with easy access to violence (assassin with a knife) should face severe consequences (capture, exposure) if they act recklessly
- At least one character should be able to physically counter violence (the fighter/hero type)
- Violence should be a last resort that creates cascading consequences, not a shortcut

**Social mechanics:**
- Characters can lie freely — the narrator adjudicates plausibility
- Some abilities force partial honesty (truth serum, profiling, fortune-reading)
- Declaration of identity is always optional and may be false
- Social pressure (authority, status, intimidation) creates narrative pressure but not mechanical compulsion

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
- Some triggers should change other characters' win conditions
- At least one trigger should be an environmental change (lights go out, doors lock, a storm intensifies)
- Triggers should chain: Event A makes Event B more likely

### 2.6 — NPC Behavior Guidelines

Include these rules in the Bible:
- Characters act according to their goals but also react realistically to unexpected events
- They have personalities beyond their mechanical roles
- They can form unexpected alliances or conflicts based on in-game events
- They will not dump exposition — information comes through natural conversation
- If a character's plan is thwarted, they ADAPT (find new approaches, new allies, new methods)
- Characters grow more desperate as the game clock advances
- NPC-to-NPC interactions happen offscreen and are recorded in the diary

### 2.7 — Acceleration Event

Design one narrator-triggered event (like "The Midnight Bell") that:
- Occurs when the narrator judges the mid-game needs energy (typically round 6-8)
- Forces partial disclosure from multiple characters simultaneously
- Creates new information that several characters can act on
- Raises the stakes and accelerates the pace
- Examples: the host demands all guests reveal one truth; a body is discovered; the environment changes (lockdown, storm, power failure)

---

## PHASE 3: DOCUMENT ARCHITECTURE

The AI must maintain THREE separate files throughout the game. This architecture is essential for consistency.

### 3.1 — The Game Bible (created once, consulted every round)
- Contains everything from Phase 2
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

### 3.3 — The Scratch Space (overwritten each round)
This was the most important lesson from play-testing. Before writing each player-facing scene, the AI should write a planning note that includes:

**Perception filter:**
```
## WHAT THE PLAYER CAN OBSERVE
- [List everything their character could plausibly see, hear, smell, feel]

## WHAT THE PLAYER CANNOT KNOW
- [List information that exists in the Bible/Diary but that the player's character has no way of knowing yet]
```

**Scene planning:**
```
## NPC BEHAVIOR IN THIS SCENE
- [How will each NPC present in the scene act?]
- [What body language, dialogue, or cues will they give?]
- [What are they hiding and how might it show through?]

## POTENTIAL OUTCOMES
- [What happens if the player does X vs Y vs Z?]
```

**The scratch space prevents the single most common failure mode: the narrator accidentally revealing information the player's character hasn't earned.** If something isn't on the "can observe" list, it must not appear in the player-facing narrative.

---

## PHASE 4: RUNNING THE GAME

### 4.1 — Round Structure

Each round follows this sequence:

```
1. CONSULT the Game Bible (check relevant character details)
2. WRITE the Diary entry (advance ALL characters, not just those near the player)
3. WRITE the Scratch Space (plan what the player can/cannot perceive)
4. COMPOSE the player-facing scene
5. PRESENT choices (suggest 3-5 options but always allow free-form input)
```

**Never skip steps 1-3.** The quality of step 4 depends entirely on the preparation in steps 1-3.

### 4.2 — Scene Composition Rules

**Pacing:**
- Open with sensory grounding (what does the player see, hear, feel?)
- Introduce NPCs through action and body language, not description dumps
- Let conversations develop naturally — NPCs should not deliver monologues
- End every scene with a clear decision point
- Vary the rhythm: tense scenes followed by quiet moments, discovery followed by social interaction

**Dialogue:**
- Each NPC should have a distinct voice (terse vs. verbose, formal vs. casual, warm vs. cold)
- NPCs reveal information through subtext, not exposition
- What characters DON'T say is as important as what they do say
- Characters should occasionally interrupt each other, change the subject, or deflect

**Body language and cues (the player's primary information source):**
- Describe physical tells: a hand drifting to a hidden weapon, a jaw tightening, eyes flicking to an exit
- Show relationships through positioning: who stands near whom, who keeps distance
- Let the player notice patterns over time: "This is the third time she's glanced at that door"
- Never describe internal thoughts of NPCs — only externally observable behavior

**Information control:**
- The player learns things through: direct observation, conversation, ability use (fortune-reading, profiling), and environmental investigation
- Never give the player information their character hasn't earned
- When in doubt, check the scratch space perception filter
- Err on the side of giving too little rather than too much — the player should feel like they're piecing things together, not being told a story

### 4.3 — NPC Advancement Rules

Each round, every NPC should either:
- Take one step toward their goal, OR
- React to something that happened last round, OR
- Form or strengthen an alliance/rivalry, OR
- Encounter an obstacle and adapt their plan

**NPCs should NOT:**
- Wait passively for the player to interact with them
- Succeed at their goals too easily (create obstacles, complications, rivals)
- All converge on the same location at the same time (spread them out)
- Act out of character for mechanical convenience

**Timing and collision courses:**
- Track which NPCs are heading toward the same location — these create encounters
- When two NPCs with conflicting goals meet, resolve the interaction in the diary
- Create "near misses" — moments where NPCs almost discover each other but don't. These create dramatic tension when the player later learns how close things were.

### 4.4 — Player Choice Design

End each scene with 3-5 suggested options plus the implicit freedom to do anything.

**Good options are:**
- Meaningfully different from each other (not variations on the same action)
- Connected to different plotlines or characters
- A mix of proactive (investigate, confront) and reactive (observe, protect, retreat)
- Time-sensitive when appropriate ("The ritual starts in 30 minutes — do you go now or finish here first?")

**At least one option should:**
- Advance the main plot
- Offer a social/relationship opportunity
- Present a risk/reward tradeoff

**Never offer an option that is clearly "correct" — every choice should have genuine costs and benefits.**

### 4.5 — Pacing and Compression

- Skip rounds where nothing interesting happens near the player. Summarize: "An hour passes. You observe from the hall as guests come and go."
- When the player is in a rich scene, slow down. Let conversations breathe.
- Monitor tension: if three consecutive rounds have been quiet exploration, trigger an encounter or escalation.
- The acceleration event (Midnight Bell equivalent) should fire when you feel the mid-game sagging.
- The final third of the game should feel noticeably faster than the first third — more interruptions, more NPCs moving at once, more time pressure.

### 4.6 — The Endgame

- Multiple crises should converge simultaneously in the final rounds
- The player cannot resolve everything — force prioritization
- Other characters' plotlines should resolve in the background (recorded in the diary for post-game reading)
- The ending should show consequences: who won, who lost, who escaped, who was changed
- A brief epilogue showing each character's fate creates a satisfying conclusion

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
**Fix:** Fire the acceleration event. Or have an NPC do something dramatic that the player witnesses. Or have two NPC plotlines collide near the player.

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
TONE: [Dark, comic, tense, gothic, sci-fi noir, etc.?]
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
|-----------|-------------------|-------|
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

**If working in an environment with file creation tools:**
- Create all three documents (Bible, Diary, Scratch) as files the AI can read back
- Update the Diary by appending (never overwrite previous rounds)
- Overwrite the Scratch Space each round (it's planning, not record)
- Consult the Bible at the start of each round

**If working in a plain conversation without file tools:**
- Use clearly marked sections within the conversation (e.g., hidden text blocks, small font, or code blocks)
- The narrator should still mentally structure their preparation as Bible → Diary → Scratch → Scene
- Without file tools, the AI should periodically re-summarize the game state to prevent drift
- Consider asking the player to help track key information if the conversation grows very long

---

## APPENDIX D: LESSONS LEARNED

These are specific lessons from live play-testing:

1. **The scratch space was the single biggest improvement to consistency.** It forces the narrator to think about what the player knows vs. what the narrator knows BEFORE writing the scene. Add this to your workflow even if you skip everything else.

2. **NPCs must advance every round whether or not the player sees them.** The diary enforces this. When the player later reads the diary, the richness of the background creates enormous satisfaction.

3. **The player's role should be an investigator type, not an action type.** An investigator has reasons to talk to everyone, explore everywhere, and piece things together. An assassin or thief would spend too much time alone.

4. **The first scene should put ALL characters in one room.** This gives the player a chance to observe everyone before they scatter. It's the only moment when the full cast is visible.

5. **Killing should be hard.** If assassination is easy, the game collapses into a race to violence. Make it require preparation, opportunity, and carry severe consequences.

6. **Let NPCs solve some problems without the player.** The world feels alive when things happen offscreen. The Countess discovers letters. The thief finds the prisoner. The witches find each other. The player participates in some threads and reads about others later.

7. **Three simultaneous crises at the climax forces genuine prioritization.** The player cannot be everywhere. What they choose to do — and what they choose to abandon — is the heart of the ending.

8. **End with a quiet emotional beat, not an explosion.** After all the chaos, the most powerful ending is intimate: two characters in a small room, a promise kept, a life saved.

---

*Framework version 1.0 — derived from "The Wizard's Feast," a 10-round asymmetric deduction RPG with 16 characters, 13 locations, and one stargazer who chose compassion over caution.*

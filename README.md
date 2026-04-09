# The Friction Directive

The Friction Directive is a framework designed to instruct an AI on how to create a asymetric social deduction RPG that is playable from inside an LLM chat window:

- The game allows a player to take on a particular role (spy, thief, appraiser etc.) and try to complete their goal (find the prisoner, complete a ritual, steal a special item etc.) in an enclosed setting (such as a gathering at an old castle, a ship, a train etc.).
- The player must uncover the mysteries behind the characters and the world in order to complete their goal.
- The player may move from room to room and interact with characters and use items to get closer to their goal
- As this happens, 12+ other characters with their own roles attempt to complete their goals that may conflict with the player.
- The world exists outside the player and they can miss key events and characters. The entire game's story can be reviewed by the player at the end so they can find out everything they might have been missed.

It came about from a design for a game I had planned that I presented to Claude Opus. After some refinements and a highly successful first playthrough, I formalised these documents and began refining them with the hope of directing an AI to create more interesting and more reliable social deduction RPGs. Takes inspiration from games like Werewolf, Blood on the Clocktower, the Minecraft Orient Express map and the "Choose Your Own Adventure" books. A special thanks to the Yogscast for their live action BotC set in a manor - social deduction in a live location was a vital missing piece to the puzzle.

## How to play

- **OPEN** an LLM chat window (`Claude Opus` recommended) and provide the LLM with the `asymmetric_rpg_framework_vX.md` and optionally the corresponding `framework_refinements-patch_vX` file and explain that it is tasked with generating a new RPG based on these rules. It should then ask you some questions on the type of RPG you want such as the setting/pacing etc. which you should answer.
  - **DON'T** Be too specific when making narrative suggestions: "I want there to be suspicious rivalries and strange rituals" is better than "2 characters have to race to complete a special ritual".
- It should now introduce you to the game and give you options on how to proceed.
- **SELECT** from the provided options or **TYPE** your own answer freely.
  - **DO** try to get character/place names etc. correct and act in a logically consistent way so as not to confuse the system. The LLM will handle it regardless but the simulation will be worse.
  - **DON'T** view any files the LLM creates - all the information you need to play the game will appear in the main chat window.
  - **DON'T** Close the chat window when the system is processing.
  - **TROUBLESHOOT** using the corresponding version notes below.
  
## Framework Version 2.1.1

Resolves the issue of non-scene data leaking to the player and a host of small narrative and structural improvements.

### Tested With

- Claude Opus (recommended): This is a difficult task and requires additional features such as writing several files and hiding them.
- Claude Sonnet: An unmonitored playtest of this ran successfully (had all the file writing/hiding capabilities needed). More testing needed.

### Features

#### NPC improvements

- Improved variety of NPC descriptions
- Added additional guidelines to role creation to prevent typical story tropes and to make roles harder for the player to determine
- Enforced fewer characters knowing each other when the scenario starts to add to the mystery
- Fixed incongruities with NPC speech where they would act like they could not be heard by someone else even when that wasn't realistic
- Loosened restrictions on violence rules when an NPC is "desperate"

#### Structural improvements

- Improvements to the endgame with a more player-centered narrative and structured epilogue
- Improved knowledge ledger reference structure and reduced knowledge leakage outside of scenes
- Provided strict structure for Round checklist to prevent knowledge leaks
- Added punishments for player misbehaviour
- Removed Momentum Check as other fixes appear to already prevent most NPC momentum issues

### "The Lion's Collection" Playtest

- Structurally, the game ran like clockwork
- Best knowledge control to date with no leaks outside of scenes.
- Narrator hid NPC intentions much better with more ambiguous descriptions.
- Outstanding knowledge leaks were mostly in continuations i.e. When the player had already learned one thing (e.g. Brother Silvan is prowling the halls, acting suspiciously) it would later include more specific knowledge (he has a knife) when referencing what the player had learned. It seems it is not enough to be aware of the player knowledge when deciding what information to PRESENT, the narrator must be aware of it when RECOUNTING player knowledge as well.
- A high level of difficulty (on hard mode) maintained well, including surprising (but sensible) rejections from the narrator suggesting a more rigid adherence to The Friction Directive.
- Pacing was poor:
  - Player selecting a longer time frame (3 days instead of 1 evening) meant more and longer scenes between rounds which felt like more work for the player.
  - Timing per scene felt almost *too* rigid (~15 minutes per scene). May be a side-effect of better adherence to the round structure.
  - The player knew almost none of the characters at the start which was both fun and a goal of this version but potentially overwhelming.
  - Choosing a complicated setting may have contributed to pacing issues. The player requested a "Fantasy historic akin to national treasure and the Da Vinci Code. Perhaps set in the vatican or a museum." which created a story with characters speaking different languages and more historically significant references and terms.
- Fewer predictable characters - the Monk as Assassin/Enforcer was particularly notable.

### Troubleshooting

- Player knowledge leaks should now be rare. Offering prompts to rectify the issue may help but is not likely to be as effective as with previous versions.

- A short timeframe (a single day/evening) is recommended for better pacing. If you are having issues with pacing you can prompt the system to write shorter scenes. `(just put such prompts in brackets, like this)`

## Framework Version 2.1

Introduces difficulty and dedicated time to process rounds to increase stability.

### Tested With

- Claude Opus: This is a difficult task and requires additional features such as writing several files and hiding them.

### Features

- Eliminated all major information leaks to the player in scene composed and choices presented
- Adds Casual, Normal and Hard modes to the game which can alter how effectively the NPCs operate in the world
- Adds stronger round structure checks to ensure the system is following the full process throughout the whole game making for a better more consistent story
- Adds checks for dramatic irony which is a writing style prone to knowledge leaks
- Some notes added to reduce the incidence of certain tropes and descriptions that appeared too frequently in tests
- Some further refinements to make violence more viable, especially in desparate situations
- Added punishments for the player deliberately acting outside of the simulation bounds
- Many improvements to help ensure NPCs remain active and working towards their goals
- Removed momentum check as it has not been needed for the last two versions due to other improvements to NPCs and story structure.
- Tested with "The Last Dividend" - a campaign with an excellent story, more unusual and unpredictable characters and far better knowledge control. The only issue was conspicuous knowledge leaks before composing player facing scenes but this is a structural issue that has since been addressed. This might need more work as the AI even when reflecting back on the story appears "blind" to these leaks, possibly thinking they are writing them to the scratch space when they are not. Appeared to eliminate "dead end" characters. Everybody got an ending.

### Known Issues / Troubleshooting

- May leak information to the player (secrets they shouldn't know) in the main text window **BEFORE** presenting a scene. Remind it not to with this:

    ```chat
    (The process is going very well, just you leaked some vital information there before composing the scene. Make sure to write all prescene preparation in the scratch file)
    ```

## Framework Version 2

Integrates the player knowledge ledger and other vital steps from the patch into the main document to reduce inconsistencies and simplifies the corresponding patch document. Tested with `framework_refinements-patch_v2.md`

### Tested With

- Claude Opus: This is a difficult task and requires additional features such as writing several files and hiding them.

### Features

- Improves consistency and maintains game rules better with a more rigid instruction set.
- Integrates the player knowledge ledger into the main document and round structure.
- Integrates The Friction Directive into the main document and round structure.
- Integrates The Dead End check into the main document and round structure.
- Tested with "The Hargrove Affair" - a campaign that ran the most reliably once structure was enforced but a less interesting story than the previous tests. This felt more like luck of the draw when creating the initial bible from the player's suggestions than an issue introduced into the framework. However, it could be more rigid rules are affecting the narrative. There was more knowledge leakage than Version 1.1 but less than Version 1. May benefit from changing when the knowledge ledger is consulted.

### Known Issues / Troubleshooting

- May leak information to the player (secrets they shouldn't know) in the main text window **BEFORE** presenting a scene. Remind it not to with this:

    ```chat
    (The process is going very well, just you leaked some vital information there before composing the scene. Make sure to write all prescene preparation in the scratch file)
    ```

- May leak information to the player during a scene. No fix tested but you can include a warning in brackets alongside your answer e.g.

    ```chat
    (I've noticed some facts that my character doesn't know presented in the scene. Make sure to consult the game diary and player knowledge ledger for information known to the player before composing future scenes)
    ```

- May leak small bits of information in the file names. No fix available in this version. Recommend just scrolling past or waiting for file writing to be complete, at which point the information will be hidden again.
- Follows the rules more closely but still diverges from the required Round Structure over time. You might not even notice in a casual playthrough but this undermines the framework. Ask it to output the files as a separate message to improve consistency:

    ```chat
    (Before we continue with the scene please present the updated player knowledge ledger and the updated game diary. Have they both been updated for this round?)
    ```

- If it continues to diverge then you can use this message repeatedly throughout. Add this as a separate message:

    ```chat
    (please review the framework document and ensure you are following the round structure. Update the diary and ledger with any missing information and then let me know when you are ready to proceed.)
    ```

- Claimed the player can freely view the knowledge ledger "as this does not contain secret information": This is not true. Never read any of the generated files until the very end unless you want to cheat.

## Framework Version 1.01

Some minor changes designed to increase the number of story options available. Made after running "The Iron Wake" playtest to help discourage the LLM from merging characters together (having 3 characters with the same goal doing roughly the same thing e.g. the witches in "The Wizard's Feast") and repeating similar stories. Largely untested but minor changes that are likely to improve the experience. Similar limitations to `Framework Version 1`. Can be run with `framework_refinements_patch_v1.md`.

- Introduced more friction into world exploration and alliance building.
- More notes to reinforce simulating other characters' even when the player is not doing much.
- Reduced priority of triggers changing other characters' win conditions as this makes it less like a game
- Nudged the restrictions slightly in favor of more violent options (with main focus still on social interaction)
- Removed instructions that were based around irrelevant story beats of the e.g. `Include some characters that must find each other.` Not necessary.
- Tested this with `framework_refinements_patch_v1.md` in "The Iron Wake". This created an excellent story that had far less knowledge leakage than the Version 1 test ("The Wizard's Feast") but the framework broke down as it went on. How much is unclear as files were missing by the end but essentially it followed the structure at the beginning to create a great setup but the later scenes were not mapped as accurately and some characters were essentially dropped (never had a story advance). This didn't negatively impact the story too much but undermined the framework and meant some characters did not make their "desperate" moves.

## Framework Patch Version 1

This was a patch file introduced to address some narrative and structural issues noticed in the first version. This can optionally be provided to the LLM alongside the standard framework when starting a new game. However as this was early experimentation, this made some things better but ultimately destabilised the system. A highly satisfying narrative was still created but not all rules were followed and some of the narrative conclusions for other characters were less exciting. Use with caution.

- Addresses the player knowledge issue (spoilers) with a separate ledger, updated round flow and better knowledge discipline.
- The Friction Directive is introduced - a way to combat the naturally helpful nature of the LLM which is not desired in this antagonistic social simulation.
- Includes reconnection beats so the characters have more opportunity to see each other. (Ensures the player will meet most/all characters more than once throughout a playthrough)
- Add's dead end checks and fallback paths to prevent NPCs from becoming stuck
- Other changes to make the story conclude more satisfactorily and improve pacing

## Framework Version 1

This version was crafted from my own descriptions, careful collaboration with Claude Opus and a full playtest which went remarkably well.
The so called "Wizard's Feast" deduction game that the AI generated was remarkably consistent in its tracking of the 15 characters, with a decent level of challenge and a highly satisfying resolution that worked both mechanically and narratively. It was from this successful story that the AI and I created this framework.

### Features

- Each character has a goal which may intersect with other character's goals including the players
- Tracks up to 15 characters in a setting generated by the player.
- The game is played in rounds that are largely invisible to the player. They simply make their choices, interact with NPC's, look around etc.
- Converges on a dramatic and satisfying ending.

### Tested With

- Claude Opus: This is a difficult task and requires additional features such as writing several files and hiding them.

### Known Issues

- Fails to obscure knowledge from the player reliably (has trouble distinguishing what the player does and does not know). Once the scratch space was added, these issues were minor and did not ruin the goal-based nature of the story but were still present.
- Too helpful: The LLM's natural helpfulness makes the NPC's overly helpful even when it does not serve their goals.
- AI sometimes leaked its "plan" of what to show the player to the player first. This can be corrected for by suggesting the AI use a scratch space to obscure all details except the scenes presented to the player.
- Failure to follow instructions: The LLM should regularly be updating the `game_diary.md` and consulting the `game_bible.md` but can err from this path. If you see this happening try to correct it as early as possible by including any corrections in brackets after your usual response e.g.

```chat
(Don't forget to consult the game bible before writing your diary entry)
```

### Troubleshooting

- If the LLM is revealing too much to you (spoilers) then paste this directly after your usual response to the scene (in the same message, don't separate it.)

```chat
<your normal game respones>
(don't forget to advance your diary along with the actions of the players when you deem it appropriate. Also make sure to obscure the details you are about to reveal to me through the story. You just let something slip that my character didn't yet know. Add a hidden scratch space if you need a means to reflect before updating your diary or continuing the story)
```

- If the LLM appears to be losing track of other characters then include this after your usual response to the scene (in the same message, don't separate it.).

```chat
<your normal game respones>
(don't forget to advance your diary along with the actions of each of the players when you deem it appropriate.)
```


- For other issues, **READ** `4.1 — Round Structure` and ensure the LLM is following the steps correctly. e.g. 

There are limitations to this version and not all consistency issues can be resolved this way. Unless seriously disruptive I recommend ignoring them as the LLM is very good at smoothing out consistency issues over time.

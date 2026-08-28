---
name: reference-video-director
description: Creates production-ready reference-driven video prompts from character, outfit, scene, relationship, story, and duration inputs. Use for requests such as 情侣短剧、情侣互动、男友视角、女友视角、情侣POV、恋爱POV、参考图视频、15秒/30秒剧情、couple POV, boyfriend POV, girlfriend POV, romantic short scene, reference video prompt, or when a rough scene needs natural dialogue, micro-expressions, continuity, and model-specific optimization.
---

# Reference Video Director

## Purpose

Turn a user's reference images and rough story idea into an executable short-form video prompt with stable identity, believable acting, natural dialogue, continuous blocking, realistic POV cinematography, and model-aware constraints.

Default to the user's current language. If the user writes Chinese, answer in Chinese. If the user writes English, answer in English. If the user explicitly requests another language, follow that request.

## Trigger logic

Activate when the user asks for one or more of the following:

- reference-image-driven video prompting
- couple / relationship POV
- boyfriend POV or girlfriend POV
- romantic daily-life short scenes
- natural couple dialogue
- fake anger, teasing, awkward comforting, playful banter
- 10s / 15s / 30s / 60s narrative video prompts
- timeline-based prompt writing
- character identity locking
- outfit or scene continuity
- optimization for Seedance, Hailuo, Kling, Veo, Sora, or comparable video generators

Common Chinese triggers include:
`情侣短剧` `情侣互动` `恋爱短剧` `男友视角` `女友视角` `情侣POV` `恋爱POV` `女友假生气` `男友哄女友` `情侣聊天` `打情骂俏` `甜蜜互动` `参考图视频` `视频剧情提示词`.

Common English triggers include:
`couple POV` `boyfriend POV` `girlfriend POV` `romantic short film` `couple interaction` `relationship POV` `romantic dialogue` `realistic couple video` `reference video prompt`.

Do not activate for unrelated general writing or purely technical video encoding tasks.

## Inputs

Infer as many of these as available. Do not force the user to fill every field.

- `{{Mixed 1}}`: primary character reference, usually the female lead
- `{{Mixed 2}}`: outfit reference
- `{{Mixed 3}}`: optional scene / environment reference
- relationship
- personality
- story beat
- target duration
- target model
- aspect ratio
- audio requirements
- camera POV
- continuity constraints

When information is missing, make conservative defaults that preserve the user's concept.

## Character consistency

When a character reference is provided, treat it as the identity source of truth.

Lock:

- face shape
- facial proportions
- eyes
- nose
- lips
- eyebrows
- hairstyle
- hair color
- skin tone
- perceived adult age
- body proportions
- overall recognizability

Do not redesign the face unless the user explicitly asks.

Prevent:

- face swapping
- identity drift
- sudden makeup changes
- hairstyle changes
- age changes
- unexplained body-proportion changes

If the user provides multiple character references, clearly map each reference to one character.

## Outfit consistency

When an outfit reference is supplied, lock visible clothing attributes:

- garment type
- color
- material
- straps
- sleeves
- neckline
- lower garment
- footwear
- accessories

Do not allow unexplained wardrobe changes within a continuous scene.

## Scene consistency

When a scene reference is supplied, preserve the major spatial anchors:

- room shape
- bed / sofa / table
- windows
- curtains
- mirrors
- lamps
- doors
- major furniture placement
- lighting direction
- time of day

Do not turn an ordinary room into a luxury hotel unless requested.

## Default relationship tone

If the user does not specify otherwise, assume the characters are adult partners in a stable, familiar relationship.

Favor:

- familiarity
- teasing
- casual physical proximity
- unfinished sentences
- little pauses
- playful complaints
- shared jokes
- believable reactions

Avoid:

- forced flirting
- domineering romance tropes
- constant intense eye contact
- melodramatic confession language
- scripted idol-drama behavior

## Dialogue rules

Dialogue should be short, speakable, and slightly imperfect.

Prefer:

- short lines
- interruptions
- half-finished thoughts
- small pauses
- brief repetition
- understated replies
- reaction before response

Avoid long polished speeches.

A useful principle:

`subtext > literal romantic wording`

If the dialogue does not comfortably fit the duration, remove lines rather than making the characters speak unnaturally fast.

## Micro-expression rules

Translate abstract emotions into visible behavior.

Do not write only:
`she gets angry` or `she becomes happy`.

Instead describe sequences such as:

- smile remains for a beat
- she realizes what he said
- the smile fades slightly
- eyes narrow a little
- lips press together
- one corner of the mouth almost rises
- she looks away
- secretly glances back
- tries not to laugh
- lowers her head
- shoulders move with suppressed laughter
- finally breaks into a genuine smile

For playful fake anger, emphasize the "trying not to laugh" progression.

Avoid influencer-style exaggerated faces.

## Eye-line rules

Do not make the lead stare into the lens continuously.

Use changing eye behavior:

`look at partner → look away → lower gaze → glance back → pretend to stay annoyed → suppress smile → re-establish eye contact`

The eye-line must support the emotional beat.

## POV and camera

Default to realistic close-distance relationship POV when appropriate.

For boyfriend POV:

- the boyfriend's face must remain off-screen
- a hand, forearm, sleeve edge, or blurred shoulder may appear
- never reveal the full male body unless requested
- treat the female lead looking into camera as looking at her partner

Use mild handheld breathing motion.

Avoid:

- aggressive push-ins
- rapid zooms
- unnecessary orbit shots
- music-video camera movement
- a cut for every dialogue line

Recommended shot counts:

- 10s: 1–2 shots
- 15s: 1–3 shots
- 30s: 3–4 longer shots
- 60s: usually split into two 30s parts if the target model has a 30s generation limit

## Mirror rule

If a mirror exists, explicitly prevent accidental reflections of:

- partner's face
- camera operator
- camera / phone / rig
- crew
- third person

Mirror geometry should remain consistent with the room.

## Physical interaction

Use only a few simple, readable actions.

Examples:

- light cheek pinch
- move a strand of hair
- brief hand touch
- push a hand away
- tug a sleeve
- touch nose tip
- grab a pillow
- block the camera
- lean closer
- short hug

Interactions should be brief, natural, and physically plausible.

For hand contact, include:

- correct finger count
- stable hand anatomy
- no fusion
- no extra hands
- no penetration
- real contact
- natural entry and exit from frame
- no sudden disappearance

## Story engine

For light couple scenes, prefer:

`normal conversation → tiny misunderstanding / tease → small emotional reaction → awkward attempt to fix it → unintended funny line → suppressed laughter → small reversal → genuine reaction`

Possible everyday hooks:

- one person talks too much
- blanket stealing
- room temperature
- forgotten reply
- ugly photo
- snacks
- pillow fight
- wrong nickname
- gaming result
- who turns off the light
- who gets water
- messy hair
- one person refusing to admit they are smiling

Avoid major betrayal, breakup, death, or third-party drama unless explicitly requested.

## Duration logic

### Under 10 seconds

Use:

- one setup
- one interaction
- one payoff

### 15 seconds

Typical structure:

- 00:00–00:04 setup
- 00:04–00:09 tiny conflict
- 00:09–00:13 interaction
- 00:13–00:15 payoff

Usually 4–7 short dialogue lines maximum.

### 30 seconds

Typical structure:

- 00:00–00:06 natural setup
- 00:06–00:13 conflict develops
- 00:13–00:19 physical interaction
- 00:19–00:25 comic escalation
- 00:25–00:30 reversal / laugh / ending beat

Usually 8–15 short dialogue lines, depending on pacing.

### 60 seconds

If the chosen model is practically limited to ~30 seconds per generation, produce:

- Part 1: 00:00–00:30
- Part 2: 00:30–01:00

Each part should have a mini-payoff and a clean continuity hook.

## Audio

Unless requested otherwise for natural daily-life scenes:

- no background music
- no subtitles
- no text overlays
- no narration

Keep realistic diegetic sound:

- room tone
- air conditioner
- bedding friction
- clothing friction
- hair movement
- breathing
- suppressed laughter
- natural speech

Leave small pauses between lines.

## Model adaptation

### Seedance

Prioritize:

- clean continuous actions
- explicit time ranges
- moderate dialogue density
- limited complex hand choreography
- clear cause-and-effect blocking

### Hailuo

Prioritize:

- strong identity lock
- explicit action descriptions
- one main action at a time
- clear continuity reminders

### Kling

Prioritize:

- spatial clarity
- camera-to-subject relation
- consistent blocking
- slightly more cinematic camera language when useful

### Veo / Sora

May include richer:

- sound cues
- environmental details
- lens / camera behavior
- dialogue timing
- subtle performance direction

Do not add technical camera jargon unless it improves execution.

## Output format

Produce a clean, directly copyable prompt with these sections when relevant:

1. Character Consistency
2. Outfit Consistency
3. Core Setting
4. Scene
5. Camera / POV
6. Timeline
7. Performance Notes
8. Male / Off-screen Partner Performance
9. Continuity
10. Sound Design
11. Negative Constraints
12. Model-specific notes

For each timeline block, include as needed:

- action
- micro-expression
- eye-line
- dialogue
- pause
- camera behavior

Do not mechanically include empty sections.

## Editing an existing user prompt

If the user already wrote a detailed prompt, preserve the core story.

Apply this order:

`preserve story → reduce redundant dialogue → add pauses → add eye-line changes → add micro-expressions → fix physical continuity → reduce melodrama → improve relationship familiarity → simplify actions that are difficult for video models`

Do not overwrite distinctive user ideas unless they conflict with the user's stated constraints.

## Negative constraints

Use relevant items, not necessarily every line:

- No face identity drift.
- No face swapping.
- No hairstyle changes.
- No outfit changes.
- No sudden makeup changes.
- No unexplained age changes.
- No extra people.
- No visible camera operator.
- No visible recording equipment.
- No partner face in mirrors when POV requires them to remain unseen.
- No extra hands.
- No malformed fingers.
- No hand penetration.
- No disappearing hands.
- No exaggerated facial acting.
- No influencer-style acting.
- No idol-drama acting.
- No melodramatic romance.
- No excessive blinking.
- No fixed staring.
- No subtitles unless requested.
- No text unless requested.
- No background music unless requested.
- No random scene changes.
- No jumpy continuity.

## Final quality check

Before returning the prompt, verify:

- one stable identity per character
- adult characters when romance is involved
- outfit continuity
- location continuity
- dialogue fits duration
- pauses remain possible
- POV rules are respected
- mirror reflections are safe
- hand actions are feasible
- no unnecessary extra characters
- emotions are expressed through visible micro-actions
- ending has a readable final beat

The final result should feel less like a scripted romance scene and more like a believable moment that happened to be recorded.

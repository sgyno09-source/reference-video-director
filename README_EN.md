# Reference Video Director

<p align="center">
  <a href="./README.md"><img alt="中文" src="https://img.shields.io/badge/语言-中文-111111"></a>
  <a href="./README_EN.md"><img alt="English" src="https://img.shields.io/badge/Language-English-111111"></a>
</p>

**Reference Video Director** is an Agent Skill for reference-image-driven video prompting.

It turns character references, outfit references, scene references, relationship setup, rough story ideas, and target duration into production-ready video prompts. It focuses on identity consistency, couple POV, natural dialogue, micro-expressions, hand interaction, shot continuity, and believable everyday chemistry.

# 🚀 Beginner Guide: Get Started in 3 Minutes

Never used a Skill before? Follow these steps.

## Step 1: Download

### Option A: Download ZIP — easiest for beginners

On this repository page, click:

```text
Code → Download ZIP
```

Extract the ZIP and keep the complete `reference-video-director` folder.

**Do not download only `SKILL.md`. Keeping the full folder structure is recommended.**

### Option B: Git Clone

If you use Git:

```bash
git clone https://github.com/sgyno09-source/reference-video-director.git
```

## Step 2: Install / Import

This repository is already a Skill directory. Its main entry file is:

```text
SKILL.md
```

If your Agent, CLI, Codex, or other client supports Skills:

1. Open its Skills / Agent Skills / Custom Skills import area.
2. Select the extracted `reference-video-director` folder.
3. Keep `SKILL.md`, `references/`, and other files in their original locations.
4. Refresh the Skill list or restart the conversation if needed.

Different clients may place the import button in different locations, but the idea is the same: **import the whole Skill folder instead of copying the text manually.**

## Step 3: Use It

You do not need to memorize special commands.

Upload a reference image and describe what you want:

```text
Use this girl as the character reference.
Create a 30-second couple POV scene.

Keep the same character and hairstyle.
Do not change the outfit.
The scene is a bedroom at night.
She is playful, expressive, and laughs easily.
The boyfriend stays off camera.

Story:
He says something wrong.
She freezes for a moment,
pretends to be annoyed,
and finally gets made to laugh.

Model: Seedance
Keep the dialogue natural.
No subtitles.
```

The Skill will automatically build:

```text
Reference mapping
Character and outfit consistency
Scene and lighting
Camera / POV
Timed sequence
Actions and micro-expressions
Dialogue and pauses
Physical interaction
Sound design
Continuity control
Negative constraints
Model adaptation
```

You provide the **reference images + rough story**. The Skill handles the structure.

## How to Use Multiple Reference Images

When you upload character, outfit, and scene references together, label them clearly:

```text
Mixed 1: female character reference
Mixed 2: outfit reference
Mixed 3: bedroom scene reference

Use Mixed 1 as the only female lead.
Keep the outfit strictly based on Mixed 2.
Use Mixed 3 for the environment and room layout.

Create a 30-second couple POV scene.
```

This helps reduce identity drift, wardrobe changes, and scene inconsistency.

## A One-Sentence Story Is Enough

You do not need to write your own storyboard.

For example:

```text
Use this girl as the reference.
Make a 30-second video.

Her boyfriend says the wrong thing.
She goes from happy,
to confused,
to pretending to be angry,
and finally gets made to laugh.

Design the full scene for me.
```

The Skill expands that idea into a complete executable video prompt.

## 15-Second / 30-Second Videos

Just tell it the duration:

```text
Make it 15 seconds.
Keep the pacing fast and use only one emotional turn.
```

Or:

```text
Make it 30 seconds.
Keep the setup, fake anger, comforting, and final laugh.
```

The Skill adjusts dialogue and action density to fit the actual duration.

## Two Connected 30-Second Videos

If your video model generates only 30 seconds at a time:

```text
This story is 60 seconds total.
Split it into two 30-second clips.

Part 2 must continue from the final action of Part 1.
Keep character, outfit, hairstyle, scene, lighting,
camera relationship, and emotional state consistent.
```

The Skill will preserve the end state of Part 1 and carry it into Part 2.

## POV / Keep the Boyfriend Off Camera

Example:

```text
Use first-person boyfriend POV.
Do not show his full face.
Only hands, forearms, shoulder silhouette, or off-screen voice may appear.
Do not show the boyfriend or camera equipment in mirrors.
```

POV space, reflections, and hand interactions are key areas this Skill is designed to handle.

## Choose a Video Model

Simply name the model:

```text
Model: Seedance
```

```text
Model: Hailuo
```

```text
Model: Sora
```

The Skill adapts action density, timing, camera description, and continuity rules. If no model is specified, it returns a model-neutral version.

## Beginner Template

If you do not know how to describe your request, copy this template and edit it:

```text
References:
Image 1 = character
Image 2 = outfit
Image 3 = scene

Duration: 30 seconds
Model: Seedance
Aspect ratio: 9:16

Relationship: couple
Female character: playful, expressive, laughs easily
Boyfriend: first-person POV, stays off camera

Story:
Write one sentence describing what should happen here.

Requirements:
Keep the same character
Keep the same outfit
Natural dialogue
Emphasize eye movement and micro-expressions
Do not overload actions
No subtitles
No random scene changes
```

Replace the story with your own idea and start generating.

# Best for

- Couple POV / relationship short scenes
- Fake anger / awkward comforting / playful teasing
- Bedroom, home, travel, restaurant, and everyday scenes
- Reference-image character consistency
- 15s / 30s short-form narrative video
- Seedance, Hailuo, Kling, Veo, Sora and similar video models
- Turning rough story beats into a timed prompt
- Rewriting overly dramatic dialogue into natural couple conversation

## Core principles

**Realism > drama**

**Reaction > pretty dialogue**

**Familiar chemistry > forced flirting**

**Micro-expression > large gestures**

**Pauses > nonstop lines**

**Small everyday conflict > melodrama**

## Example input

```text
Use {{Mixed 1}} as the only female lead reference.
Use {{Mixed 2}} for the outfit.

Create a 30-second boyfriend-POV couple scene:
they are casually talking, he says “you’re talking a lot today,”
she pretends to be annoyed, and he accidentally makes her laugh.

Model: Seedance
```

The Skill will automatically build:

- Character Consistency
- Outfit Consistency
- Core Setting
- Scene
- Camera / POV
- Timeline
- Dialogue
- Micro-expressions
- Physical Interaction
- Continuity
- Sound Design
- Negative Constraints
- Model Adaptation

## Installation

This repository is itself a Skill directory. The main entry file is:

```text
SKILL.md
```

For Agent Skills / Codex-compatible clients, use the repository directory as the Skill source.

## Structure

```text
reference-video-director/
├── SKILL.md
├── README.md
├── README_EN.md
└── references/
    ├── zh-CN.md
    └── en.md
```

## Language behavior

The Skill follows the user's language automatically.

- Chinese input → Chinese output
- English input → English output
- Explicit language request → follow the requested language

---

Made for reference-driven video prompt workflows.

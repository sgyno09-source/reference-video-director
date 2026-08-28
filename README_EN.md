# Reference Video Director

<p align="center">
  <a href="./README.md"><img alt="中文" src="https://img.shields.io/badge/语言-中文-111111"></a>
  <a href="./README_EN.md"><img alt="English" src="https://img.shields.io/badge/Language-English-111111"></a>
</p>

**Reference Video Director** is an Agent Skill for reference-image-driven video prompting.

It turns character references, outfit references, scene references, relationship setup, rough story ideas, and target duration into production-ready video prompts. It focuses on identity consistency, couple POV, natural dialogue, micro-expressions, hand interaction, shot continuity, and believable everyday chemistry.

## Best for

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

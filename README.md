# Reference Video Director

<p align="center">
  <a href="./README.md"><img alt="中文" src="https://img.shields.io/badge/语言-中文-111111"></a>
  <a href="./README_EN.md"><img alt="English" src="https://img.shields.io/badge/Language-English-111111"></a>
</p>

**Reference Video Director** 是一个面向参考图驱动视频创作的 Agent Skill。

它会根据角色参考图、服装参考图、场景参考图、人物关系、剧情想法和目标时长，生成更适合视频模型直接执行的完整提示词，重点处理人物一致性、情侣 POV、自然对白、微表情、手部互动、镜头连续性与真实生活感。

## 适合什么

- 情侣 POV / 恋爱短剧
- 女友假生气 / 男友哄人
- 居家、卧室、旅行、餐厅等生活化场景
- 参考图角色一致性
- 15 秒 / 30 秒短剧情
- Seedance、Hailuo、Kling、Veo、Sora 等视频模型
- 将粗略剧情改造成时间轴 Prompt
- 将“太像演戏”的对白改得更自然

## 核心原则

**真实感 > 戏剧性**

**人物反应 > 漂亮台词**

**情侣默契 > 强行暧昧**

**微表情 > 大动作**

**停顿 > 连续念台词**

**小事情 > 大冲突**

## 输入示例

```text
使用 {{Mixed 1}} 作为唯一女主角参考，
服装参考 {{Mixed 2}}。

做一个 30 秒男友 POV 情侣短剧：
女友本来在聊天，男友说“你今天话好多”，
女友开始假生气，最后被男友一句话逗笑。

模型：Seedance
```

Skill 会自动完成：

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

## 安装

这个仓库本身就是一个 Skill 目录，核心入口文件是：

```text
SKILL.md
```

兼容 Agent Skills / Codex Skill 风格的客户端，可直接使用仓库目录作为 Skill 来源。

## 目录

```text
reference-video-director/
├── SKILL.md
├── README.md
├── README_EN.md
└── references/
    ├── zh-CN.md
    └── en.md
```

## 语言

Skill 会自动跟随用户当前使用的语言。

- 中文输入 → 中文输出
- English input → English output
- 用户明确指定语言 → 按指定语言输出

---

Made for reference-driven video prompt workflows.

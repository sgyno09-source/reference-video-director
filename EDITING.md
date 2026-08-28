# Editing Guide / 编辑说明

[中文](#中文编辑说明) · [English](#english-editing-guide)

---

## 中文编辑说明

这份说明用于维护 `reference-video-director`，避免在扩展 Skill 时破坏触发逻辑、输出结构和参考图一致性规则。

### 1. 主要文件

- `SKILL.md`：核心执行逻辑。所有触发词、默认行为、时间轴规则、镜头规则、模型适配都应优先在这里修改。
- `README.md`：中文项目介绍，只负责解释用途、安装和调用方式，不要把完整执行逻辑重复一遍。
- `README_EN.md`：英文项目介绍，应与中文 README 保持功能一致。
- `references/zh-CN.md`：中文调用示例和补充说明。
- `references/en.md`：英文调用示例和补充说明。

### 2. 修改 Skill 时的顺序

推荐按下面顺序编辑：

1. 先判断修改属于“触发”“执行逻辑”“模型适配”还是“文档说明”。
2. 涉及实际行为时，优先修改 `SKILL.md`。
3. 如果用户可见能力发生变化，再同步更新中英文 README。
4. 新增复杂示例时，优先放进 `references/`，不要让 `SKILL.md` 变成示例合集。
5. 修改后检查中英文描述是否仍然对应。

### 3. 触发词怎么改

触发词应该描述“用户真正会怎么说”，而不是堆大量同义词。

例如可以增加：

```text
旅行情侣短片
餐厅情侣互动
reference character video
romantic daily-life POV
```

不要加入过宽的词，例如：

```text
视频
图片
恋爱
导演
```

否则 Skill 很容易在不相关任务里误触发。

### 4. 执行逻辑怎么改

新增规则时，优先保持下面的层级：

```text
输入识别
→ 人物一致性
→ 服装 / 场景一致性
→ 人物关系和表演
→ 镜头 / POV
→ 时间轴
→ 声音
→ 模型适配
→ Negative Constraints
→ 最终检查
```

不要把同一条规则同时写在多个章节里。重复规则只保留最明确的一处，必要时用一句简短引用提醒。

### 5. 时间轴规则

时间轴必须服务于模型可执行性，而不是单纯写故事。

每个时间段尽量包含：

- 角色动作
- 眼神
- 微表情
- 对白
- 停顿
- 镜头行为

如果内容超出时长，优先删对白，不要要求人物加速念台词。

### 6. 人物一致性规则

任何新增功能都不要破坏这些基础约束：

- 同一角色不换脸
- 五官比例不漂移
- 发型和发色连续
- 服装连续
- 年龄感不跳变
- 场景空间关系不跳变
- 镜子中不意外出现摄影者
- 手部互动必须有真实接触关系

如果某个新功能需要故意换装、变妆、年龄变化或角色转换，应明确写成“用户显式要求时才允许”。

### 7. 对白与表演

Skill 的核心不是写漂亮台词，而是把真实反应写清楚。

优先保留：

- 停顿
- 抬眼
- 移开视线
- 偷偷看回来
- 抿嘴
- 忍笑
- 低头
- 肩膀轻动
- 自然破功

减少：

- 连续长句
- 偶像剧式情话
- 霸总台词
- 每句话都在撩人
- 夸张网红表情

### 8. 新增模型适配

如果要新增视频模型，例如未来增加某个新模型，建议只写该模型真正有区别的部分。

模板：

```markdown
### Model Name

Prioritize:

- xxx
- xxx
- xxx

Avoid:

- xxx
```

不要复制整套通用规则到每个模型下面。

### 9. 中英文同步

`SKILL.md` 可以保持英文主结构并包含中英文触发词。

README 和 references 应尽量同步功能，但不要求逐字翻译。重点是两种语言看到的功能、限制和使用方式一致。

### 10. 提交建议

Commit message 建议保持简单：

```text
feat: add travel couple scene logic
fix: improve hand interaction continuity
docs: update Chinese usage examples
refactor: simplify trigger rules
```

### 11. 修改前最后检查

提交前确认：

- YAML 头部仍然存在且格式正确
- `name` 仍为 `reference-video-director`
- `description` 能清楚说明什么时候触发
- 没有把示例写成硬性剧情
- 默认逻辑仍然允许用户覆盖
- 15s / 30s 时长仍然可执行
- 中英文 README 没有明显功能差异
- 没有加入互相冲突的规则

---

## English Editing Guide

This file explains how to maintain `reference-video-director` without breaking its trigger logic, prompt structure, or reference-consistency rules.

### 1. Main files

- `SKILL.md`: the source of truth for behavior, triggers, defaults, timelines, camera logic, and model adaptation.
- `README.md`: Chinese project overview.
- `README_EN.md`: English project overview.
- `references/zh-CN.md`: Chinese usage examples and notes.
- `references/en.md`: English usage examples and notes.

### 2. Recommended edit order

1. Decide whether the change affects triggers, execution logic, model adaptation, or documentation.
2. If behavior changes, edit `SKILL.md` first.
3. If user-visible capability changes, update both READMEs.
4. Put longer examples in `references/` instead of bloating `SKILL.md`.
5. Verify that Chinese and English documentation still describe the same capabilities.

### 3. Trigger editing

Triggers should reflect realistic user phrasing.

Good additions:

```text
travel couple short film
restaurant couple interaction
reference character video
romantic daily-life POV
```

Avoid overly broad triggers such as:

```text
video
image
romance
director
```

Broad triggers increase false activation.

### 4. Execution-logic structure

Keep new rules in this order when possible:

```text
input parsing
→ character consistency
→ outfit / scene consistency
→ relationship and performance
→ camera / POV
→ timeline
→ audio
→ model adaptation
→ negative constraints
→ final quality check
```

Avoid duplicating the same rule across multiple sections.

### 5. Timeline editing

A timeline should improve model executability, not just tell a story.

Each time block should include, when useful:

- action
- eye-line
- micro-expression
- dialogue
- pause
- camera behavior

If the content does not fit the requested duration, remove dialogue before increasing speaking speed.

### 6. Identity continuity

Do not break these defaults when adding features:

- no unexplained face changes
- stable facial proportions
- stable hair and hair color
- outfit continuity
- stable perceived age
- stable scene geometry
- no accidental camera-person reflection
- physically plausible hand contact

Intentional transformations should only happen when explicitly requested by the user.

### 7. Dialogue and performance

The Skill should prioritize visible reactions over polished romantic writing.

Favor:

- pauses
- glances
- looking away
- glancing back
- pressed lips
- suppressed laughter
- natural emotional breakdown

Reduce:

- long speeches
- idol-drama dialogue
- domineering romance tropes
- constant flirting
- exaggerated influencer acting

### 8. Adding model adapters

Only document behavior that is genuinely model-specific.

Suggested format:

```markdown
### Model Name

Prioritize:

- xxx
- xxx
- xxx

Avoid:

- xxx
```

Do not duplicate all universal rules under every model.

### 9. Bilingual maintenance

`SKILL.md` may keep an English primary structure while including both Chinese and English trigger phrases.

The README and reference files do not need literal translations, but their capabilities, limits, and usage guidance should remain equivalent.

### 10. Commit style

Suggested commit messages:

```text
feat: add travel couple scene logic
fix: improve hand interaction continuity
docs: update Chinese usage examples
refactor: simplify trigger rules
```

### 11. Pre-commit checklist

Before committing, confirm:

- YAML front matter is valid
- `name` is still `reference-video-director`
- `description` clearly explains when the Skill should trigger
- examples have not become hard-coded story requirements
- users can still override defaults
- 15s / 30s outputs remain realistically executable
- Chinese and English READMEs remain functionally aligned
- no contradictory rules were introduced

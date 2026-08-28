# Reference Video Director

<p align="center">
  <a href="./README.md"><img alt="中文" src="https://img.shields.io/badge/语言-中文-111111"></a>
  <a href="./README_EN.md"><img alt="English" src="https://img.shields.io/badge/Language-English-111111"></a>
</p>

**Reference Video Director** 是一个面向参考图驱动视频创作的 Agent Skill。

它会根据角色参考图、服装参考图、场景参考图、人物关系、剧情想法和目标时长，生成更适合视频模型直接执行的完整提示词，重点处理人物一致性、情侣 POV、自然对白、微表情、手部互动、镜头连续性与真实生活感。

# 🚀 新手 3 分钟上手

完全没用过 Skill 也没关系，按下面做就行。

## 第一步：下载

### 方法 A：直接下载 ZIP（最适合新手）

打开本仓库后，点击：

```text
Code → Download ZIP
```

下载完成后解压，得到 `reference-video-director` 文件夹。

**不要只下载 `SKILL.md`，建议保留整个文件夹结构。**

### 方法 B：Git Clone

会用 Git 的话可以直接：

```bash
git clone https://github.com/sgyno09-source/reference-video-director.git
```

## 第二步：安装 / 导入

这个仓库本身就是一个 Skill 目录，核心入口是：

```text
SKILL.md
```

如果你的 Agent、CLI、Codex 或其他客户端支持 Skills：

1. 找到它的 Skills / Agent Skills / Custom Skills 导入入口。
2. 选择刚才下载并解压的 `reference-video-director` 文件夹。
3. 保持 `SKILL.md` 和 `references/` 等文件原有位置不变。
4. 导入完成后重新打开会话或刷新 Skill 列表。

不同客户端的安装入口可能不同，但原则一样：**导入整个 Skill 文件夹，而不是把里面的文字复制出来。**

## 第三步：开始使用

安装后不需要背复杂命令。

上传参考图，然后直接告诉它：

```text
参考这张女生图
做一个30秒情侣POV

保持同一个人物和发型
服装不要变化
场景是晚上卧室
女生性格俏皮爱笑
男友不露脸

剧情：
男友说错一句话
女生先愣一下
然后假装生气
最后又被逗笑

模型：Seedance
对白自然一点
不要字幕
```

Skill 会帮你自动补全：

```text
参考图绑定
人物与服装一致性
场景与光线
Camera / POV
分秒时间轴
动作与微表情
对白与停顿
手部互动
声音设计
连续性控制
负面约束
模型适配
```

你负责给**参考图 + 大概剧情**，剩下的交给 Skill。

## 多张参考图怎么写

如果同时上传人物、服装、场景参考图，最好明确告诉它每张图负责什么：

```text
Mixed 1：女主人物参考
Mixed 2：服装参考
Mixed 3：卧室场景参考

使用 Mixed 1 作为唯一女主角
服装严格参考 Mixed 2
场景结构参考 Mixed 3

生成30秒情侣POV
```

这样可以减少换脸、换衣服、场景漂移等问题。

## 只会一句剧情也可以

不需要自己会写分镜。

例如直接说：

```text
参考这个女生
做一个30秒视频

男朋友说错一句话
她从开心到愣住
再到假装生气
最后被逗笑

帮我完整设计
```

Skill 会自动把一句话扩展成可执行的视频提示词。

## 做 15 秒 / 30 秒视频

直接告诉它时长即可：

```text
做15秒，节奏快一点，只保留一个转折
```

或者：

```text
做30秒，保留起因、假生气、哄人和最后笑出来
```

Skill 会根据时长自动控制对白和动作密度，不会把一分钟剧情硬塞进 30 秒。

## 做两个连续的 30 秒

如果模型单次只能生成 30 秒，可以这样说：

```text
这段剧情一共60秒
拆成两个30秒

第二段必须接第一段最后一个动作
人物、服装、发型、场景、灯光和情绪状态保持一致
```

Skill 会为第二段补上上一段结束时的人物位置、动作和状态，方便连续生成。

## POV / 男友不露脸怎么写

例如：

```text
男友使用第一人称POV
全程不露脸
只允许手、前臂、肩部或画外音进入画面
镜子里不要出现男友和摄影设备
```

这类空间关系、镜面和手部互动也是本 Skill 重点处理的部分。

## 指定视频模型

可以直接写模型名称：

```text
模型：Seedance
```

```text
模型：Hailuo
```

```text
模型：Sora
```

Skill 会根据模型调整动作密度、时间轴、镜头与连续性描述。没有指定模型时，会输出通用版本。

## 一个推荐的新手模板

不会写需求时，复制下面这段改内容就行：

```text
参考图：
图1是人物
图2是服装
图3是场景

时长：30秒
模型：Seedance
画幅：9:16

人物关系：情侣
女生性格：俏皮、爱笑、情绪写在脸上
男友：不露脸，第一人称POV

剧情：
这里写一句你想发生的事情

要求：
保持同一人物
保持同一服装
对白自然
加强眼神和微表情
动作不要太密
不要字幕
不要突然换场景
```

把最后的剧情换成自己的想法，就可以开始用了。

# 适合什么

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

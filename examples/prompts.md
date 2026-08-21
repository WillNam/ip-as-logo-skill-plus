# Example Prompts

Copy-ready examples for agents and users. Replace `<product>` with actual product name/context.

---

## 中文示例

### 品牌风格参考（原创）

```text
为 <product> 设计一个 IP 吉祥物 logo。
参考方向：腾讯企鹅的「友好、社交、圆润」气质，但必须完全原创，不能复制 QQ 企鹅。
背景：科技蓝。生成 6 个候选，三个方向各 2 个。
```

```text
做一个类似美团风格的本地生活 App 吉祥物：紧凑、跳跃感、日常实用。
颜色：黄色 IP + 炭灰，背景 sage green。
要求：32×32 可识别，三语义色，无商标复制。
```

```text
B 站 ACG 社区 vibe 的原创吉祥物：屏幕/天线元素，粉色 + 白色，背景天蓝。
不要复制 22/33 或小电视 logo。
```

### 行业模板

```text
这是一个 fintech 产品 <product>，请按 industry-templates 提出 3 个方向并生成 6 张 logo。
偏好：信任感、安全感，不要攻击性造型。
```

```text
AI Agent 工具 <product>，需要一个 spark/ghost 方向的吉祥物。
背景 deep navy，IP 色 violet + cyan，保持三语义色规则。
```

### 指定主体

```text
Create a rounded ghost IP logo on deep navy background for <product>.
Three directions, six candidates: A1–C2.
```

---

## English examples

### Brand-inspired (original only)

```text
Design an original mascot logo for <product> inspired by Spotify's music/rhythm vibe.
Use green family IP colors on charcoal background. Do NOT copy the Spotify circle mark.
Propose 3 directions, then generate 6 candidates.
```

```text
Slack-like team-collab energy for <product>, but fully original rounded hash-blob creature.
Two semantic IP colors + one background. Six independent square assets.
```

### Industry template

```text
EdTech product <product>. Use industry-templates/edtech.
Propose owl, book-worm, and lighthouse directions. Generate A1–C2 after I approve.
```

---

## Single-direction deep dive

When user picks one direction and wants 6 variants:

```text
Direction B approved: "Coin owl — smart savings — belly coin disc".
Generate B1–B6 with controlled variation in:
- eye size (small vs medium)
- belly disc placement (center vs lower)
- background (3 different OKLCH-compliant chromatic backgrounds)
Keep silhouette and complexity budget identical.
```

---

## Two-color explicit request

```text
Two-color logo only: one IP base (charcoal) + cream background.
Facial marks as negative-space cutouts. No third semantic color.
Subject: simplified robot head with visor.
```

---

## Brand preset quick reference

| Prompt snippet | Loads preset |
|----------------|--------------|
| "腾讯风格" / "QQ企鹅气质" | Tencent |
| "阿里/电商感" / "淘宝感" | Alibaba |
| "字节/抖音感" | ByteDance |
| "B站/二次元" | Bilibili |
| "微信绿" | WeChat |
| "京东狗气质" | JD |
| "小红书种草感" | Xiaohongshu |
| "拼多多/社交电商" | Pinduoduo |
| "百度搜索感" | Baidu |
| "滴滴出行感" | DiDi |
| "知乎知识感" | Zhihu |
| "Apple 极简" | Apple |
| "Nike 运动感" | Nike |
| "ChatGPT/AI助手气质" | OpenAI vibe |
| "GitHub 开发者感" | GitHub |

Agent: always read `references/brand-presets.md` for full palette and do-not-copy rules.

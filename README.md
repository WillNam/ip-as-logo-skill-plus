# IP as Logo Plus

在 [s1dashu/ip-as-logo-skill](https://github.com/s1dashu/ip-as-logo-skill) 基础上优化增强的 Agent Skill：生成高度简化的 IP 吉祥物 logo，并内置 **20+ 知名公司品牌风格预设**（腾讯、阿里、B 站、Apple、Spotify 等），方便快速产出有辨识度的原创方向。

遵循开放 Agent Skills 格式，兼容 Codex、Cursor 等 Agent 环境。

![IP as Logo showcase](assets/ip-as-logo-wall.webp)

## 相比原版的增强

| 能力 | 原版 | Plus |
|------|------|------|
| 核心 logo 规范 | ✅ | ✅ 保留并结构化 |
| 品牌风格预设库 | ❌ | ✅ 20+ 公司/行业锚点 |
| 行业模板 | ❌ | ✅ fintech / edtech / AI 等 |
| 示例 Prompt | ❌ | ✅ 中英双语 |
| 商标规避规则 | 基础 | ✅ 强化 do-not-copy 清单 |
| 中英 README | EN | ✅ 双语 |

> **重要：** 预设仅作**设计方向参考**，输出必须是**原创**吉祥物，不得复制任何注册商标图形。

## 安装

```bash
npx skills@latest add <your-github-username>/ip-as-logo-skill-plus
```

全局安装：

```bash
npx skills@latest add <your-github-username>/ip-as-logo-skill-plus --global
```

或手动复制 `SKILL.md` 及 `references/`、`examples/` 到项目的 `.cursor/skills/` 或 `.codex/skills/` 目录。

## 使用

### 品牌风格参考

```text
为我的 App 设计一个腾讯风格的原创企鹅吉祥物 logo，背景科技蓝，生成 6 个候选。
```

Agent 会读取 `references/brand-presets.md` 中的 Tencent 预设，提取圆润、社交、配色等方向，**但不会复制 QQ 企鹅商标**。

### 行业模板

```text
这是一个 fintech 产品，请提出 3 个 IP 方向并生成 6 张 logo。
```

### 自由创作

```text
Create a rounded ghost IP logo on deep navy background.
```

## 内置品牌预设（部分）

**中国互联网：** 腾讯、阿里、字节跳动、美团、B 站、微信、京东、小米、华为、网易

**全球：** Apple、Google、Meta、Amazon、Spotify、Slack、Discord、Nike、Starbucks、Coca-Cola

完整列表见 [`references/brand-presets.md`](references/brand-presets.md)。

## 仓库结构

```text
SKILL.md                          # 主 Skill 指令
references/
  brand-presets.md                # 知名公司风格预设
  industry-templates.md           # 行业 IP 模板
examples/
  prompts.md                      # 中英示例 Prompt
assets/
  ip-as-logo-wall.webp            # 展示图
README.md
LICENSE
```

## 核心规范（摘要）

- 一个主导圆角轮廓，约 6–10 个基础形
- 默认三语义色：2 个 IP 色 + 1 背景色
- 三个方向 → 六张独立候选（A1–C2）
- 75–85% 角落构图，配对特征必须完整
- Flat-first + 连续渐变微体积（OKLCH L 变化 ≤ 0.08）
- 禁止复制商标、禁止 contact sheet 拼版

## 上传到 GitHub

```bash
cd ip-as-logo-skill-plus
git add .
git commit -m "Initial release: IP as Logo Plus with brand presets"
git remote add origin https://github.com/<your-username>/ip-as-logo-skill-plus.git
git push -u origin main
```

## 致谢

基于 [s1dashu/ip-as-logo-skill](https://github.com/s1dashu/ip-as-logo-skill)（MIT）fork 并增强。

## License

MIT — 见 [LICENSE](LICENSE)

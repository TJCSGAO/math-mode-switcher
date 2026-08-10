# math-mode-switcher

`math-mode-switcher` 是一个用于 **切换公式输出模式（渲染 / 源码 / 双模式）** 的 TraeWork Skill。它把“看最终公式排版效果”和“拿可复制公式代码”这两类需求明确分开，显著降低人与 AI 在数学公式沟通上的歧义和往返成本。

[中文说明](./docs/zh-CN.md) | [English Guide](./docs/en.md)

## Why this skill

在大多数 AI 对话里，公式交互常常会出现三个典型问题：

- 你想看公式渲染效果，AI 却输出了一段 ` ```latex ` 代码块
- 你想复制可直接用于 `LaTeX` / `PDF` / `Word` 的源码，AI 却只给渲染结果
- 你既要检查视觉效果，又要立即复制源码，但 AI 没有稳定的双模式约定

这个 Skill 的目标就是把这些场景标准化，让用户只需要一句非常短的口令，就能得到期望格式的输出。

## Core capabilities

- `渲染模式`：直接展示数学公式的排版效果，推荐使用 `$...$` 与 `$$...$$`
- `源码模式`：输出可复制的公式代码，支持 `Markdown` 与 `LaTeX`
- `双模式`：先看渲染效果，再拿可复制源码
- 默认策略：未明确指定时，根据用户意图自动推断最合理的输出方式

## Typical use cases

- 检查别人给的 LaTeX 公式最终长什么样
- 为论文、专利、技术文档、PDF 排版准备可直接复制的公式源码
- 在协作场景中统一“公式该怎么展示”的沟通口令
- 降低复杂数学表达在 AI 对话中的误解率

## Repository structure

```text
.trae/
  skills/
    math-mode-switcher/
      SKILL.md
docs/
  zh-CN.md
  en.md
README.md
LICENSE
```

## Installation

将本仓库中的 `.trae/skills/math-mode-switcher/` 目录复制到你的工作目录下即可。

如果你的工作目录已经使用 Trae 自定义技能结构，最终应满足：

```text
<your-workspace>/.trae/skills/math-mode-switcher/SKILL.md
```

## Quick start

推荐直接在对话里使用以下固定口令：

- `模式：渲染`
- `模式：源码（md）`
- `模式：源码（latex）`
- `模式：双模式`

## Design principles

- **低歧义**：把“渲染展示”和“源码输出”显式区分
- **低摩擦**：优先使用最短、最稳的用户口令
- **可复制**：适合在论文、专利、报告、PDF 工作流中直接复用
- **跨模型通用**：尽量采用对多数 AI 都稳定的表达约定

## Documentation

- [中文详细说明](./docs/zh-CN.md)
- [English documentation](./docs/en.md)

## License

MIT

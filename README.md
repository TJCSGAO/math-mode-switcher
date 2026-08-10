# math-mode-switcher

一个用于 **切换公式输出模式（渲染 / 源码 / 双模式）** 的 TraeWork Skill：解决“想看渲染效果”和“想复制源码”之间反复切换的沟通成本。

## 你会得到什么

- `渲染模式`：行内 `$...$`，块级 `$$...$$`，避免 ```latex``` 代码块导致不渲染
- `源码模式`：输出可复制的 `Markdown` 或 `LaTeX` 公式代码（可用于论文/专利/PDF/Word 工作流）
- `双模式`：先渲染再源码，一边确认样式一边复制

## 文件结构

```
.trae/
  skills/
    math-mode-switcher/
      SKILL.md
```

## 安装方法（本地）

把本仓库的 `.trae/skills/math-mode-switcher/` 目录复制到你的工作目录即可。

## 使用口令（推荐）

- `模式：渲染`
- `模式：源码（md）` 或 `模式：源码（latex）`
- `模式：双模式`

## License

MIT


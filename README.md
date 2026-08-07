# 小红书 AI 知识图文 Skill

![小红书 AI 知识图文](xiaohongshu-ai-knowledge-post/assets/column-banner.png)

一个 Codex Skill，用来把 AI 概念、文章、截图、文件和混合笔记整理成经过核验、面向小白的小红书知识图文。

它包含：

- 先做选题判断，不盲目总结素材；
- 使用一手来源核验 AI 概念；
- 统一的 3:4 手绘视觉系统；
- 固定的拉拉与猫咪角色规范；
- 从真实修改反馈沉淀的生图评测集与回归用例；
- 图片加载、正式话题、AI 内容声明和最终确认等发布检查。

## 安装

将 `xiaohongshu-ai-knowledge-post` 复制到 Codex 的 skills 目录，然后这样调用：

```text
使用 $xiaohongshu-ai-knowledge-post，把这个 AI 关键词或素材整理成小红书知识图文。
```

## 目录结构

```text
xiaohongshu-ai-knowledge-post/
├── SKILL.md
├── agents/openai.yaml
├── assets/column-banner.png
└── references/
    ├── content-workflow.md
    ├── eval-set.md
    ├── publish-checklist.md
    └── visual-system.md
```

## 开源协议

MIT

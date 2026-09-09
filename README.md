# 统计与 AI 概念学习仓库

用「溯源原始出处 → 可视化 → 递进自测」的方式，学习 **Agent、大模型的上下文、Skill** 三个 AI 核心概念。所有论断都附可点击的原始出处链接，供随时验证。

## 仓库用途

1. **学习资料**：`learning-materials/` 下有 3 份单页 HTML 概念资料 + 2 份概念关系说明（HTML 图文版 / Markdown 渲染版），设计原则是"少即是多"——概念少、文字少、颜色少，降低认知负荷
2. **可复用方法论**：`.workbuddy/skills/` 下沉淀了一个项目级 Skill，以后学任何新概念都能用同一套流程生成同风格的资料

## Skill 的存放路径与调用方式

- 路径：`.workbuddy/skills/concept-learning-guide/SKILL.md`（项目级，仅本仓库生效）
- **在 WorkBuddy 中调用**：在本仓库目录下打开 WorkBuddy 会话，直接说：
  - 「帮我做一份关于 XX 概念的学习资料」
  - 或明确点名：「用 concept-learning-guide 生成一份关于 XX 的学习资料」
- Skill 会自动执行：溯源原始出处（2-3 个一手来源）→ 先写学习目标与核心问题 → 提炼章节 → 按模板生成 → 出 6 道递进测试题 → 按 8 项自检清单核对后交付

## 已生成的学习资料

| 文件 | 主题 | 原始出处 |
|------|------|----------|
| `learning-materials/agent.html` | Agent（智能体）：与 Workflow 的区别、三组件架构、使用边界 | [Anthropic《Building effective agents》](https://www.anthropic.com/engineering/building-effective-agents)、[Lilian Weng《LLM Powered Autonomous Agents》](https://lilianweng.github.io/posts/2023-06-23-agent/) |
| `learning-materials/llm-context.html` | 大模型的上下文：注意力预算、context rot、三种长任务技术 | [Anthropic《Effective context engineering for AI agents》](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)、[Lilian Weng（记忆部分）](https://lilianweng.github.io/posts/2023-06-23-agent/) |
| `learning-materials/skill.html` | Skill：SKILL.md 格式、渐进式披露、与 MCP/RAG 的区别 | [Anthropic 工程博客（概念首发）](https://www.anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills)、[agentskills.io 开放规范](https://agentskills.io/specification) |
| `learning-materials/concept-relationship.html` | 三概念关系（图文版） | 汇总以上来源 |
| `learning-materials/concept-relationship.md` | 三概念关系（Mermaid 渲染版） | 同上 |

每份概念资料均含：概念的个人解释、核心机制（SVG 图）、一个具体应用场景、易混淆问题与使用边界、可核查的来源链接、6 道难度递进的自测题（★☆☆ → ★★★，点击即时判分）。

## 使用 AI 后的人工核查和修改

本仓库由 AI 辅助生成，以下是我的核查与修改记录：

### 我做过的核查

1. **交叉验证**：比对 Lilian Weng 的 "Planning / Memory / Tool use" 与 Anthropic 的 "retrieval / tools / memory"，确认是同一架构的两种表述而非冲突说法，并在资料图注中说明
2. **字段级核对**：Skill 资料中的 `name ≤ 64 字符`、`description ≤ 1024 字符`、"不能有连续连字符"等约束，逐条对照 [agentskills.io 规范 §Frontmatter](https://agentskills.io/specification#frontmatter) 原文核验
3. **来源可用性验证**：所有引用链接均确认指向真实存在的原始文章；生成中发现 platform.claude.com 文档站有地区限制，改用 agentskills.io 开放规范作为一手来源
4. **引文保真**：资料中的英文引文（如 "LLMs dynamically direct their own processes and tool usage"、"context rot" 的定义）均从原文页面提取，可点击各节末尾"出处 ↗"当场验证

### 我做过的修改

1. **结构补齐**：AI 初版只有"概念/机制/心法"三节，按本仓库要求补充了"应用场景""易混淆与使用边界"两节，并为每个概念撰写了带个人视角的"我的理解"段落
2. **测试题校准**：核对 6 道题的难度递进（★☆☆ 记忆 → ★★☆ 理解 → ★★★ 应用/辨析），确认每题解析都附溯源链接；干扰项优先采用规范原文中的真实反例
3. **Skill 通用化**：将 SKILL.md 改写为通用流程——输入任意新概念都能复用，并新增"学习目标与核心问题"的先行设计，输出结构固化为 8 项自检清单
4. **安全清理**：`.gitignore` 排除了令牌、密钥、凭据文件及含对话记录的 WorkBuddy 记忆目录，确认仓库中无任何 API Key 或个人隐私信息

<!-- ✍️ 提交前请在此处追加你本人实际做的核查记录（例如：你逐一点开验证了哪些链接、亲自修改了哪些段落的表述），评审会很看重这一部分。 -->

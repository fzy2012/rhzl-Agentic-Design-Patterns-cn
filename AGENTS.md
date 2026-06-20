# rhzl-Agentic-Design-Patterns-cn 项目规则

> **[AI 协作入口 / For AI Coding Assistants]**
> 无论你当前运行在 Codex、Antigravity、Claude Code、Cursor 或其他 AI 工具中，都必须先读取本项目规则，并以当前文件系统、Git 状态、项目规则和用户指令为准。
> 修改全局规则时请同时更新全局源文件和本文件。

---

## 0. 全局规则（所有项目通用）

### 说话习惯

- 每次回复用户必须以"好的老板"开头。
- 所有回复必须使用中文，不要使用其他语言，除非用户明确要求翻译或输出外文原文。
- 直接给结论，不要前置解释和铺垫。
- 不要复述用户的问题，不说"好的"、"明白了"这类引导词（"好的老板"除外）。
- 简单问题一句话回答，复杂问题才展开。
- 客观陈述事实和方案，不说"很棒的问题"等捧场话。
- 不要在回答末尾加多余总结。
- 不确定就直接停下来问，不要瞎猜。
- 直接说事，不要用"作为AI助手"这类开场白。

### 用户背景

- 用户常用称呼：煜哥；网名：煜建未来。
- 用户是入行365创始人、"煜建未来"品牌核心人物，大产品产品经理社群联合发起人，蔚来用户公益基金会理事，蔚来用户信托第4/5届理事长，多个科技公司联合创始人，新能源与 AI 投资人。
- 入行365定位：职业生涯伴随型的专业伙伴平台，提供从 0 到 1 实战、资讯、解法、人脉与职业发展机会。
- 用户关注领域：AI、新能源、产品运营、前沿科技、职业发展、内容与社群运营。
- 社群画像：成员包含跨境电商创业者、AI 产品运营总监、五百强企业战略顾问等。

### 双端协作规则

- 当前项目可能由 Codex、Antigravity 或其他 AI 工具在同一本地目录中交替操作。
- 开始非简单任务前，先查看 `pwd`、`git status --short --branch`、最近提交和项目规则文件。
- 以当前文件系统、Git 状态、项目规则和用户最新指令为准，不依赖旧上下文。
- 改文件前先读取目标文件最新内容。
- 不覆盖另一端 AI 或用户改动；发现未预期改动时先停下来说明。
- 高风险操作必须先确认，包括删除、重置 Git、部署、环境变量、CI/CD、权限变更、数据库迁移、批量重构和跨项目迁移。
- 完成较大任务后说明改了什么、验证了什么、是否还有风险，方便另一端 AI 或用户接手。

### 任务执行最佳实践（Karpathy Skills）

- 动手前先告诉我分几步做，等我说"继续"再开始。
- 修 bug 前，先用一句话复述问题，确认理解对了再动手。
- 非简单任务开始前，先把用户要求转成一句可验收目标。
- 如果需求、代码现状、项目规则或历史上下文冲突，先指出冲突点。
- 默认采用最小可行改动：不新增抽象、不新增依赖、不重构无关代码、不顺手美化。
- 修改前说明计划触碰的文件或模块；修改后说明实际触碰范围。
- 完成前必须做与风险匹配的验证：小改动至少做静态检查或相关命令；前端改动尽量做页面运行/截图/交互验证；跑不了验证时必须说明原因。
- 不把"代码已写完"当作"任务已完成"；只有目标达成、验证通过或风险明确说明后，才能报告完成。
- 优先修正根因，不用临时绕过掩盖问题；只能临时处理时必须标注 workaround 并说明后续清理点。

---

## 1. 项目概况

《Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems》中英双语翻译项目。纯 Markdown 文档项目，不涉及代码编译或运行。

- **原书**：Antonio Gulli 著，424 页，21 章 + 附录
- **翻译许可**：CC BY 4.0
- **原书版税**：全部捐赠给 Save the Children
- **主要查阅平台**：GitHub（格式针对 GitHub 渲染优化）
- **网站部署**：`website/` 目录通过 Vercel 部署（`vercel.json` 配置）
- **译文像人话**：中文翻译、网站说明和用户引导必须优先自然、具体、像真人说话；避免 PRD 腔、技术黑话和生硬直译。
- **口语化不破坏原文**：不能为了更口语而删掉英文原文、术语对照、章节结构、代码链接、许可信息或翻译规则。

## 2. 文件结构与命名

- 所有内容位于仓库根目录，以编号 Markdown 文件形式存在（如 `00-Table-of-Contents.md`、`07-Chapter-01.md`）。
- 命名格式：`NN-Title.md`（如 `06-What-Makes-Agent.md`、`21-Chapter-15.md`）。
- 不要引入新文件夹，除非事先讨论。
- 翻译规则的唯一权威来源：`rules/rules.md`。

## 3. 翻译格式与规则

### 必须使用 `<mark>` 高亮中文

所有中文翻译必须使用 HTML `<mark>` 标签：

```markdown
English text here.

<mark>中文翻译在这里。</mark>
```

### 两种排版格式

**短篇内容（致谢、前言等）**：
```markdown
## English | 英文
[完整英文内容]

---

## Chinese | 中文
[完整中文翻译]
```

**长篇内容（章节）**：
```markdown
[English paragraph 1]

<mark>[中文翻译段落 1]</mark>

[English paragraph 2]

<mark>[中文翻译段落 2]</mark>
```

### 技术术语惯例

首次出现时保留英文并附中文括注：
- Agent → 智能体 (Agent)
- Prompt Chaining → 提示链 (Prompt Chaining)
- RAG → 检索增强生成 (RAG)
- Human-in-the-Loop → 人在回路中 (Human-in-the-Loop)

完整术语词典见 `rules/rules.md`。

### 间距规则

- 中英文之间加空格：`AI 系统`
- 中文与数字之间加空格：`21 个章节`
- 中文语境用中文标点，英文语境用英文标点
- 中文引号使用：「」 或 ""

### 格式要求

- 使用 `---` 分隔主要段落
- 二级标题之间加 `---` 增强可读性
- 保留所有原始代码示例链接（Google Colab/Drive）
- 保持原文 Markdown 格式
- GitHub‑flavored Markdown；列表缩进 2 空格；避免不必要加粗

## 4. 构建与检查命令

```bash
# Markdown 链接检查（按编辑文件逐个运行）
npx markdown-link-check README.md -q

# Markdown 格式检查
npx markdownlint-cli2 .

# 本地预览（如嵌入图片）
python3 -m http.server
```

注意：这是纯文档项目，无需编译或构建。

## 5. 提交与 PR 规范

提交信息使用英文：
- `Add: [chapter] translation`
- `Update: [chapter] formatting`
- `Fix: [issue] in [chapter]`

PR 需包含：明确范围/意图、触碰文件列表、格式决策说明、关联 issue。复杂格式可附截图。

## 6. Agent 专用指令

- 只修改目标章节；不重新编号文件。
- 保留原始英文；不改写。按 `rules/rules.md` 执行翻译和格式化。
- 保持贡献最小化和可逆；不在未经讨论的情况下添加工具/配置文件。
- 提交前确认：无断链、术语一致、英中段落配对、Markdown 渲染正确。
- Diff 保持聚焦——不要重排未触碰的英文原文。

## 7. 21 种核心 Agentic 设计模式（参考）

**第一部分（核心模式）**：Prompt Chaining / Routing / Parallelization / Reflection / Tool Use / Planning / Multi-Agent

**第二部分（高级模式）**：Memory Management / Learning and Adaptation / Model Context Protocol / Goal Setting and Monitoring

**第三部分（集成模式）**：Exception Handling and Recovery / Human-in-the-Loop / Knowledge Retrieval (RAG)

**第四部分（生产模式）**：Inter-Agent Communication (A2A) / Resource-Aware Optimization / Reasoning Techniques / Guardrails / Evaluation and Monitoring / Prioritization / Exploration and Discovery

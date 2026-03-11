# OpenClaw 推荐 Skill 清单

> 收集时间：2026-03-03
> 用途：覆盖日常高频场景的 OpenClaw Skill 推荐
> 数据来源：ClawHub + https://github.com/VoltAgent/awesome-openclaw-skills

---

## 快速导航

- [完全免费（纯本地运行，无需任何 API Key）](#一完全免费纯本地运行无需任何-api-key)
- [使用 OpenClaw 内置 LLM（无需额外申请）](#二使用-openclaw-内置-llm无需额外申请)
- [需要第三方 API Key](#三需要第三方-api-key)
- [工作流组合](#四工作流组合)
- [安全提醒](#五安全提醒)

---

## 前置命令（必看）

安装 CLI：
```bash
npm i -g clawhub
```

常用命令：
```bash
# 1. 搜索（推荐先搜再装，避免名字变化）
clawhub search "关键词"

# 2. 安装
clawhub install <skill-slug>

# 3. 更新全部
clawhub update --all
```

**注意**：如果安装时提示 `not found`，请使用 `clawhub search` 以最新搜索结果为准（这是生态里最常见的坑）。

---

## 补充推荐（多媒体与办公集成）

### 多媒体 Skill 选择指南

| 需求场景 | 推荐 Skill | 推荐理由 |
|---------|-----------|---------|
| **通用 AI 图像生成** | `afame` | 基于 OpenAI API，通用性最强 |
| **免费图像生成** | `beauty-generation-api` | 标注为免费，适合预算敏感场景 |
| **头像/职业照** | `ai-avatar-generation` / `ai-headshot-generation` | 针对人像优化，效果更专业 |
| **AI 音乐生成** | `ace-music` | 免费 API，门槛低 |
| **音乐编辑/混音** | `acestep` | 功能完整，支持编辑和混音 |
| **文本转播客** | `agents-skill-podcastifier` | 内容创作者实用工具 |
| **AI 视频生成** | `ai-video-gen` | 文本直接生成视频，端到端 |
| **MV 制作** | `acestep-simplemv` | 音乐+歌词自动生成视频 |

**选择建议**：
1. **优先尝试免费选项**：`beauty-generation-api`（图像）、`ace-music`（音乐）
2. **注意 API 依赖**：`afame` 等需要 OpenAI/each::sense API Key
3. **实用性优先**：`agents-skill-podcastifier` 对内容创作者很有价值
4. **视频生成成本高**：`ai-video-gen` 通常消耗较多 token，建议小批量测试

---

### 图片生成/编辑

| Skill | 功能 | 费用 | API Key |
|-------|------|------|---------|
| `afame` | AI 图像生成（OpenAI） | 按 OpenAI 计费 | 需要 |
| `beauty-generation-api` | 免费 AI 图像生成 | **免费** | 无需 |
| `ai-avatar-generation` | AI 头像生成 | 依赖 each::sense | 需要 |
| `ai-headshot-generation` | 职业照生成 | 依赖 each::sense | 需要 |
| `age-transformation` | 年龄变换 | 依赖 each::sense | 需要 |
| `album-cover-generation` | 专辑封面生成 | 依赖 each::sense | 需要 |
| `ascii-art-generator` | ASCII 艺术生成 | 免费 | 无需 |

### 音频生成/编辑

| Skill | 功能 | 费用 | API Key |
|-------|------|------|---------|
| `ace-music` | AI 音乐生成 | **免费**（ACE-Step API） | 无需 |
| `acestep` | 音乐生成/编辑/混音 | 按 ACE-Step 计费 | 可能需要 |
| `acestep-songwriting` | AI 辅助写歌 | 免费 | 无需 |
| `agents-skill-podcastifier` | 文本转播客 | 本地 TTS | 无需 |

### 视频生成/编辑

| Skill | 功能 | 费用 | API Key |
|-------|------|------|---------|
| `ai-video-gen` | AI 视频生成 | 通常需付费 | 需要 |
| `acestep-simplemv` | 音乐视频生成 | 依赖 Remotion | 可能需要 |
| `3d-model-generation` | 3D 模型生成 | 依赖 each::sense | 需要 |

### Office 文档处理（读写编辑新建）

| Skill | 支持格式 | 读取 | 编辑 | 新建 | 费用 | API Key |
|-------|---------|------|------|------|------|---------|
| `word-docx` | Word (.docx) | ✅ | ✅ | ✅ | **免费** | 无需 |
| `excel-xlsx` | Excel (.xlsx) | ✅ | ✅ | ✅ | **免费** | 无需 |
| `powerpoint-pptx` | PowerPoint (.pptx) | ✅ | ✅ | ✅ | **免费** | 无需 |
| `office-document-specialist-suite` | Word/Excel/PPT 全套 | ✅ | ✅ | ✅ | **免费** | 无需 |

**选择建议**：
1. **通用方案（推荐）**：`word-docx` + `excel-xlsx` + `powerpoint-pptx`（三件套各司其职）
2. **一站式方案**：`office-document-specialist-suite`（不想装多个就选这个）

**注意**：`docx-cn`、`xlsx-cn` 是中文优化版本，中文文档处理有问题的可以替换使用。`docx-to-md` 和 `ppt-ooxml-tool` 是专用工具（格式转换/本地化），非常规办公需求再装。

### 钉钉文档

**目前未发现**专门的钉钉文档集成 skill。建议替代方案：
1. 使用 `markdown-converter` 将钉钉文档导出后处理
2. 关注 ClawHub 更新，钉钉相关 skill 可能会在后续推出

---

## 一、完全免费（纯本地运行，无需任何 API Key）

这些 skill 完全本地运行，不依赖任何 LLM 或外部服务。

### 1. Self-Improving Agent（持续自我改进）

| 项目 | 内容 |
|------|------|
| **Slug** | `self-improving-agent` |
| **安装命令** | `clawhub install self-improving-agent` |
| **使用场景** | 长期使用 OpenClaw 时，让 AI 记住你的习惯、常见纠正和错误，实现"越用越顺手"；维护长期项目保持上下文连贯性 |
| **推荐理由** | 捕获学习、错误和纠正，实现持续改进。适合高频使用者。版本 1.0.11（较成熟） |
| **费用** | 免费（纯本地记录） |
| **API Key** | 无需 |
| **来源** | ClawHub |

**适合人群**：
- 长期使用 Claude Code/OpenClaw 的用户
- 工作流程中有重复性任务，希望 AI 记住你的偏好
- 需要维护长期项目

**不适用场景**：
- 偶尔使用、一次性任务为主
- 偏好每次从零开始，不希望 AI 有"记忆"

### 2. Openai Whisper（本地语音转文字）

| 项目 | 内容 |
|------|------|
| **Slug** | `openai-whisper` |
| **安装命令** | `clawhub install openai-whisper` |
| **使用场景** | 会议录音、播客、采访音频 → 转写 → 总结要点/行动项；视频里的人声转写（配合下载工具或视频技能） |
| **推荐理由** | **完全本地运行，无需联网，无需 API Key**，隐私友好。适合离线场景。热度：Downloads 28.6k / Stars 151 |
| **费用** | 免费 |
| **API Key** | 无需 |
| **来源** | ClawHub |

### 3. Agent Browser（自动化网页操作）

| 项目 | 内容 |
|------|------|
| **Slug** | `agent-browser` |
| **安装命令** | `clawhub install agent-browser` |
| **使用场景** | 需要"真的去网页上操作"：登录后抓数据、翻页、导出、截图存档；抓取结构化信息：页面快照、网络请求过滤/查看 |
| **推荐理由** | **本地浏览器自动化**，无需外部服务。热度很高：Downloads 61.4k / Stars 322 |
| **费用** | 免费 |
| **API Key** | 无需 |
| **来源** | ClawHub |

### 4. Browser Use（持久会话浏览器）

| 项目 | 内容 |
|------|------|
| **Slug** | `browser-use` |
| **安装命令** | `clawhub install browser-use` |
| **使用场景** | 表单填写、网页测试、持续多步操作（强调"会话保持"）；需要真实 Chrome profile（带登录态）去操作一些站点 |
| **推荐理由** | 本地 Chrome 控制，稳定工作流。Downloads 17.3k / Stars 44 |
| **费用** | 免费 |
| **API Key** | 无需 |
| **来源** | ClawHub |

### 5. Weather（天气查询）

| 项目 | 内容 |
|------|------|
| **Slug** | `weather` |
| **安装命令** | `clawhub install weather` |
| **使用场景** | 快速查询当前天气、天气预报；出行前查目的地天气；自动化工作流中根据天气做决策 |
| **推荐理由** | 实用小工具，无需配置，即装即用。适合日常查询和自动化场景 |
| **费用** | 免费 |
| **API Key** | 无需 |
| **来源** | ClawHub |

### 7. Markdown Converter（Office 转 Markdown）

| 项目 | 内容 |
|------|------|
| **Slug** | `markdown-converter` |
| **安装命令** | `clawhub install markdown-converter` |
| **使用场景** | Word（.docx）、PPT（.pptx）、Excel（.xlsx/.xls）转成 Markdown；也支持 HTML/CSV/JSON/XML、图片（EXIF/OCR）、音频（转写）、YouTube URL |
| **推荐理由** | **本地文件转换**，覆盖日常办公文档。热度：Downloads 13.3k / Stars 81 |
| **费用** | 免费 |
| **API Key** | 无需 |
| **来源** | ClawHub |

### 8. Pdf（PDF 工程化处理）

| 项目 | 内容 |
|------|------|
| **Slug** | `pdf` |
| **安装命令** | `clawhub install pdf` |
| **使用场景** | 从 PDF 抽取文本/表格、批量处理报告；合并/拆分、生成新 PDF；PDF 表单填写（合同、申请表、报销单） |
| **推荐理由** | **本地 PDF 处理**，无需外部服务 |
| **费用** | 免费 |
| **API Key** | 无需 |
| **来源** | ClawHub |

### 9. Find Skills（帮你找 skill）

| 项目 | 内容 |
|------|------|
| **Slug** | `find-skills` |
| **安装命令** | `clawhub install find-skills` |
| **使用场景** | 你提出"有没有能做 X 的技能？"时，让它先帮你筛选、再建议安装 |
| **推荐理由** | 元技能，帮你发现更多能力。Downloads 72.7k / Stars 326 |
| **费用** | 免费 |
| **API Key** | 无需 |
| **来源** | ClawHub |

### 10. Github（代码仓库管理）

| 项目 | 内容 |
|------|------|
| **Slug** | `github` |
| **安装命令** | `clawhub install github` |
| **使用场景** | issue/PR/CI 查询与操作、用 gh CLI 做自动化 |
| **推荐理由** | 使用本地 gh CLI，无需额外 API Key。Downloads 61.9k / Installs 1.2k |
| **费用** | 免费 |
| **API Key** | 无需（使用本地 gh CLI 认证） |
| **来源** | ClawHub |

### 11. Skill Creator（Skill 开发工具）

| 项目 | 内容 |
|------|------|
| **Slug** | `skill-creator` |
| **安装命令** | `clawhub install skill-creator` |
| **使用场景** | 把公司流程/个人工作流固化成 skill（比如"每周报生成器""投标文件检查器"） |
| **推荐理由** | 自己开发/修改 skill 时必备 |
| **费用** | 免费 |
| **API Key** | 无需 |
| **来源** | ClawHub |

### 12. Word-Docx（Word 文档处理）

| 项目 | 内容 |
|------|------|
| **Slug** | `word-docx` |
| **安装命令** | `clawhub install word-docx` |
| **使用场景** | **读取、编辑、新建** Word 文档，保持正确的结构、样式和跨平台兼容性；适合自动化报告生成、批量文档处理 |
| **推荐理由** | **纯本地处理**，完整的读写编辑能力。跨平台兼容性好。中文文档处理有问题可换 `docx-cn` |
| **费用** | 免费 |
| **API Key** | 无需 |
| **来源** | ClawHub |

### 13. Excel-Xlsx（Excel 表格处理）

| 项目 | 内容 |
|------|------|
| **Slug** | `excel-xlsx` |
| **安装命令** | `clawhub install excel-xlsx` |
| **使用场景** | **读取、编辑、新建** Excel 文件，正确处理类型、日期、公式，保持跨平台兼容性；适合数据分析、报表生成 |
| **推荐理由** | **纯本地处理**，完整的读写编辑能力，支持复杂的 Excel 功能。中文表格处理有问题可换 `xlsx-cn` |
| **费用** | 免费 |
| **API Key** | 无需 |
| **来源** | ClawHub |

### 14. PowerPoint-PPTX（PPT 创建编辑）

| 项目 | 内容 |
|------|------|
| **Slug** | `powerpoint-pptx` |
| **安装命令** | `clawhub install powerpoint-pptx` |
| **使用场景** | **读取、编辑、新建** PowerPoint 演示文稿，幻灯片管理、布局设计、图表插入、批量处理；适合自动化演示文稿生成 |
| **推荐理由** | **纯本地处理**，完整的读写编辑能力，基于 python-pptx。需要 PPT 本地化/翻译功能可装 `ppt-ooxml-tool` |
| **费用** | 免费 |
| **API Key** | 无需 |
| **来源** | ClawHub |

### 15. Office-Document-Specialist-Suite（Office 综合套件）

| 项目 | 内容 |
|------|------|
| **Slug** | `office-document-specialist-suite` |
| **安装命令** | `clawhub install office-document-specialist-suite` |
| **使用场景** | **读取、编辑、新建** Word/Excel/PPT 全套文档；不想装多个 skill 时的"一站式"方案；自动化报告生成、批量处理 |
| **推荐理由** | **一套工具覆盖 Office 全格式**，功能全面。纯本地处理，无需外部服务。替代方案：分开装 `word-docx` + `excel-xlsx` + `powerpoint-pptx` |
| **费用** | 免费 |
| **API Key** | 无需 |
| **来源** | ClawHub |

---

## 二、使用 OpenClaw 内置 LLM（无需额外申请）

这些 skill 依赖 LLM 能力，但可直接使用 OpenClaw 内置/已配置的模型，**无需额外申请第三方 API Key**。

### 1. Summarize（URL/文件/音视频一把梭）

| 项目 | 内容 |
|------|------|
| **Slug** | `summarize` |
| **安装命令** | `clawhub install summarize` |
| **使用场景** | 网页资料收集：给一堆链接，统一提炼要点；PDF/音频/YouTube 总结 |
| **推荐理由** | 覆盖 web、PDF、图片、音频、YouTube。热度：Downloads 66.8k / Stars 311 |
| **LLM 要求** | 使用 OpenClaw 当前配置的模型（Claude Code 自带模型可直接使用） |
| **费用** | 依赖你的 OpenClaw 环境（Claude Code 用户免费使用） |
| **来源** | ClawHub |

**推荐配置**：
- Claude Code 用户：直接使用，无需配置
- 其他 OpenClaw 环境：确保已配置 LLM provider（可在 OpenClaw 设置中查看）

---

### 2. nano-pdf（自然语言改 PDF）

| 项目 | 内容 |
|------|------|
| **Slug** | `nano-pdf` |
| **安装命令** | `clawhub install nano-pdf` |
| **使用场景** | 改一页 PDF：改标题、修错字、替换一句话（"只有 PDF 没源文件"的场景） |
| **推荐理由** | 直接给"页码 + 指令"就能改。热度：Downloads 33.1k |
| **LLM 要求** | 使用 OpenClaw 当前配置的模型 |
| **费用** | PDF 处理本身免费；修改指令调用 LLM 产生消耗（由 OpenClaw 环境承担） |
| **来源** | ClawHub |

**推荐配置**：
- 确保 OpenClaw 已配置 LLM（Claude Code 用户可直接使用）
- 如需指定模型：运行 `clawhub configure nano-pdf`

---

## 三、需要第三方 API Key

这些 skill 需要注册第三方服务并配置 API Key 才能使用。部分服务有免费额度。

> **注意**：本章节仅保留最通用的搜索技能。Google Slides、Gog、Bili Summary、Trello 等技能因配置复杂或场景特定，暂不列入核心推荐。

### 1. Tavily Web Search（面向 AI 的网页搜索）

| 项目 | 内容 |
|------|------|
| **Slug** | `tavily-search` |
| **安装命令** | `clawhub install tavily-search` |
| **使用场景** | 需要"搜索引擎式"的结果列表；做调研：限定时间范围、news 主题、结果条数 |
| **推荐理由** | 搜索结果质量高，支持深度搜索。Downloads 76.7k / Stars 349（头部） |
| **费用** | **免费 1000 次/月**，超出需付费 |
| **API Key** | **需要** |

#### 注册与配置流程

1. **注册账号**
   - 访问 https://tavily.com
   - 点击 "Get Started" 用邮箱注册

2. **获取 API Key**
   - 登录后进入 Dashboard
   - 点击 "API Keys" 标签
   - 点击 "Create API Key"，复制生成的 key

3. **配置到 OpenClaw**
   - 运行 `clawhub configure tavily-search` 或按 skill 说明配置
   - 将 API Key 粘贴保存

4. **开始使用**
   ```bash
   # 示例：搜索特定主题
   "用 tavily-search 搜索'AI agent 2024'，限制最近一个月，返回10条结果"
   ```


---

## 四、工作流组合（照抄可用）

### 工作流 1：上网调研 → 出结论 → 整理报告

```
tavily-search 拉候选资料链接（限定日期/领域）
    ↓
agent-browser / browser-use 进站点抓关键页、截图/导出 PDF（必要时）
    ↓
summarize 把链接/PDF 汇总成"结论 + 证据 + 引用来源"
    ↓
导出为 Markdown/PDF（可配合 markdown-converter 整理格式）
```

**示例指令**：
> "用 tavily-search 搜'XXX'，选 8 篇可信来源；用 summarize 输出 1 页结论 + 3 页证据；最后整理成 Markdown 报告。"

**涉及 Key**：
- `tavily-search` → 需 Tavily Key（第三方）
- `summarize` → 使用内置 LLM（无需额外申请）

---

### 工作流 2：Word/Excel/PPT/PDF 混合材料 → 结构化整理 → 写报告

```
markdown-converter 把 docx/pptx/xlsx/pdf 转成 Markdown（统一入口）
    ↓
summarize 对转出的内容做"摘要/差异对比/风险点清单"
    ↓
【如果需要填表/改 PDF】
  - 用 pdf 做表单填写/合并拆分
  - 用 nano-pdf 做页面级文本修改
```

**示例指令**：
> "把这些文档（1.docx, 2.pptx, 3.pdf）转成 Markdown，然后对比它们关于'市场策略'的描述差异，输出差异清单。"

**涉及 Key**：
- `markdown-converter`, `pdf` → 完全免费
- `summarize`, `nano-pdf` → 使用内置 LLM（无需额外申请）

---

### 工作流 3：视频/音频 → 转写 → 总结 → 产出行动项

| 来源 | 流程 | 涉及 Key |
|------|------|----------|
| **本地音频/视频** | `openai-whisper` 转写 → `summarize` 提炼行动项 | `whisper` 免费，`summarize` 使用内置 LLM |

---

## 五、安全提醒

1. **第三方 Skills 视为不受信任代码**：OpenClaw 官方文档明确提醒，对高风险工具/不受信任输入优先沙箱隔离；secrets 注入也要谨慎。

2. **VoltAgent 列表声明**：awesome-openclaw-skills 列表强调"curated, not audited"，建议在 ClawHub 看 VirusTotal 扫描结果。

3. **优先使用 ClawHub**：openclaw/skills 大仓库本身有免责声明，里面可能包含可疑/恶意技能，更适合作为"历史归档"，下载安装优先以 ClawHub 为准。

4. **API Key 管理**：
   - 不要把 API Key 硬编码在代码里
   - 使用 OpenClaw 的 secrets 管理功能
   - 定期轮换 API Key
   - 为 Key 设置最小权限（如只读 vs 读写）

---

## 附录：快速索引

### 按费用/API 要求分类

| 分类 | Skill 列表 |
|------|-----------|
| **完全免费（纯本地）** | openai-whisper, agent-browser, browser-use, weather, markdown-converter, pdf, find-skills, github, skill-creator, self-improving-agent, word-docx, excel-xlsx, powerpoint-pptx, docx-cn, xlsx-cn, office-document-specialist-suite, docx-to-md, ppt-ooxml-tool |
| **使用内置 LLM（无需额外申请）** | summarize, nano-pdf |
| **需第三方 API Key** | tavily-search |

### 按场景分类

| 场景 | 推荐 Skill |
|------|-----------|
| 网页搜索 | tavily-search（需第三方 Key） |
| 网页浏览/截图 | agent-browser, browser-use（免费） |
| 通用总结 | summarize（内置 LLM） |
| Word/Excel/PPT 转 Markdown | markdown-converter（免费） |
| **Word 文档（读写编辑新建）** | word-docx, docx-cn（免费） |
| **Excel 表格（读写编辑新建）** | excel-xlsx, xlsx-cn（免费） |
| **PowerPoint 演示（读写编辑新建）** | powerpoint-pptx, office-document-specialist-suite（免费） |
| PDF 处理（表单/合并/拆分） | pdf（免费） |
| PDF 单页修改 | nano-pdf（内置 LLM） |
| 本地音频/视频转写 | openai-whisper（免费） |
| 天气查询 | weather（免费） |
| 代码仓库管理 | github（免费） |

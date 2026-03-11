# OpenClaw Skill 简报

> 完全免费技能清单（纯本地运行或内置 LLM）

---

## 核心工具类

### 1. Self-Improving Agent（持续自我改进）

| 项目 | 内容 |
|------|------|
| **安装命令** | `clawhub install self-improving-agent` |
| **使用场景** | 长期使用 OpenClaw 时，让 AI 记住你的习惯、常见纠正和错误，实现"越用越顺手"；维护长期项目保持上下文连贯性 |
| **注册流程** | 无需额外步骤 |

---

### 2. OpenAI Whisper（本地语音转文字）

| 项目 | 内容 |
|------|------|
| **安装命令** | `clawhub install openai-whisper` |
| **使用场景** | 会议录音、播客、采访音频 → 转写 → 总结要点/行动项；视频里的人声转写（配合下载工具或视频技能） |
| **注册流程** | 无需额外步骤 |

---

### 3. Agent Browser（自动化网页操作）

| 项目 | 内容 |
|------|------|
| **安装命令** | `clawhub install agent-browser` |
| **使用场景** | 需要"真的去网页上操作"：登录后抓数据、翻页、导出、截图存档；抓取结构化信息：页面快照、网络请求过滤/查看 |
| **注册流程** | 无需额外步骤 |

---

### 4. Browser Use（持久会话浏览器）

| 项目 | 内容 |
|------|------|
| **安装命令** | `clawhub install browser-use` |
| **使用场景** | 表单填写、网页测试、持续多步操作（强调"会话保持"）；需要真实 Chrome profile（带登录态）去操作一些站点 |
| **注册流程** | 无需额外步骤 |

---

### 5. Weather（天气查询）

| 项目 | 内容 |
|------|------|
| **安装命令** | `clawhub install weather` |
| **使用场景** | 快速查询当前天气、天气预报；出行前查目的地天气；自动化工作流中根据天气做决策 |
| **注册流程** | 无需额外步骤 |

---

### 6. Markdown Converter（Office 转 Markdown）

| 项目 | 内容 |
|------|------|
| **安装命令** | `clawhub install markdown-converter` |
| **使用场景** | Word（.docx）、PPT（.pptx）、Excel（.xlsx/.xls）转成 Markdown；也支持 HTML/CSV/JSON/XML、图片（EXIF/OCR）、音频（转写）、YouTube URL |
| **注册流程** | 无需额外步骤 |

---

### 7. PDF（PDF 工程化处理）

| 项目 | 内容 |
|------|------|
| **安装命令** | `clawhub install pdf` |
| **使用场景** | 从 PDF 抽取文本/表格、批量处理报告；合并/拆分、生成新 PDF；PDF 表单填写（合同、申请表、报销单） |
| **注册流程** | 无需额外步骤 |

---

### 8. Find Skills（帮你找 skill）

| 项目 | 内容 |
|------|------|
| **安装命令** | `clawhub install find-skills` |
| **使用场景** | 你提出"有没有能做 X 的技能？"时，让它先帮你筛选、再建议安装 |
| **注册流程** | 无需额外步骤 |

---

### 9. Skill Creator（Skill 开发工具）

| 项目 | 内容 |
|------|------|
| **安装命令** | `clawhub install skill-creator` |
| **使用场景** | 把公司流程/个人工作流固化成 skill（比如"每周报生成器""投标文件检查器"） |
| **注册流程** | 无需额外步骤 |

---

## 内置 LLM 类（无需额外申请 API Key）

### 10. Summarize（URL/文件/音视频一把梭）

| 项目 | 内容 |
|------|------|
| **安装命令** | `clawhub install summarize` |
| **使用场景** | 网页资料收集：给一堆链接，统一提炼要点；PDF/音频/YouTube 总结 |
| **注册流程** | 无需额外步骤（使用 OpenClaw 内置 LLM） |

---

### 11. Nano-PDF（自然语言改 PDF）

| 项目 | 内容 |
|------|------|
| **安装命令** | `clawhub install nano-pdf` |
| **使用场景** | 改一页 PDF：改标题、修错字、替换一句话（"只有 PDF 没源文件"的场景） |
| **注册流程** | 无需额外步骤（使用 OpenClaw 内置 LLM） |

---

## Office 文档处理类（免费）

### 12. Word-Docx（Word 文档处理）

| 项目 | 内容 |
|------|------|
| **安装命令** | `clawhub install word-docx` |
| **使用场景** | **读取、编辑、新建** Word 文档，自动化报告生成、批量处理。中文支持不好时换 `docx-cn` |
| **注册流程** | 无需额外步骤 |

---

### 13. Excel-Xlsx（Excel 表格处理）

| 项目 | 内容 |
|------|------|
| **安装命令** | `clawhub install excel-xlsx` |
| **使用场景** | **读取、编辑、新建** Excel 文件，支持公式、日期、图表。中文支持不好时换 `xlsx-cn` |
| **注册流程** | 无需额外步骤 |

---

### 14. PowerPoint-PPTX（PPT 创建编辑）

| 项目 | 内容 |
|------|------|
| **安装命令** | `clawhub install powerpoint-pptx` |
| **使用场景** | **读取、编辑、新建** PowerPoint 演示文稿，幻灯片管理、布局设计、图表插入 |
| **注册流程** | 无需额外步骤 |

---

### 15. Office-Document-Specialist-Suite（Office 综合套件）

| 项目 | 内容 |
|------|------|
| **安装命令** | `clawhub install office-document-specialist-suite` |
| **使用场景** | **一站式方案**：一套 skill 搞定 Word/Excel/PPT 全套文档的读写编辑新建 |
| **注册流程** | 无需额外步骤 |

---

## 多媒体生成类（免费）

### 16. Beauty Generation API（免费图像生成）

| 项目 | 内容 |
|------|------|
| **安装命令** | `clawhub install beauty-generation-api` |
| **使用场景** | 免费 AI 图像生成，适合预算敏感场景 |
| **注册流程** | 无需额外步骤 |

---

### 17. ASCII Art Generator（ASCII 艺术生成）

| 项目 | 内容 |
|------|------|
| **安装命令** | `clawhub install ascii-art-generator` |
| **使用场景** | 将文本或图片转换为 ASCII 艺术风格 |
| **注册流程** | 无需额外步骤 |

---

## 快速安装脚本

```bash
# 核心工具类
clawhub install self-improving-agent
clawhub install openai-whisper
clawhub install agent-browser
clawhub install browser-use
clawhub install weather
clawhub install markdown-converter
clawhub install pdf
clawhub install find-skills
clawhub install skill-creator

# 内置 LLM 类
clawhub install summarize
clawhub install nano-pdf

# Office 文档处理类（读写编辑新建）
clawhub install word-docx
clawhub install excel-xlsx
clawhub install powerpoint-pptx
# 或装全套：clawhub install office-document-specialist-suite

# 多媒体生成类
clawhub install beauty-generation-api
# clawhub install ascii-art-generator
```

---

*生成时间：2026-03-04*
*数据来源：openclaw-skills-recommendations.md*

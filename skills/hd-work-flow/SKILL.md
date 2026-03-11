---
name: hd-work-flow
description: |
  HD 本地开发工作流：用于需求开发、bug 修复、功能迭代的完整交付流程（Picasso 需求/迭代管理 + git worktree 开发 + GitLab MR + 可选发布 QA）。

  触发场景（遇到以下任何一种情况时**必须**加载本 skill）：
  - 用户提到"开发需求"、"新功能"、"做需求"
  - 用户提到"修复"、"修 bug"、"解决问题"
  - 用户提到"迭代"、"版本"、"发版"
  - 用户提供了 alidocs.dingtalk.com 或其他产品文档链接
  - 用户要求"走 Picasso 流程"、"创建需求"、"创建迭代"

  排除场景（**不**使用本 skill，按普通开发处理）：
  - 一次性页面："开发一个贺卡页面"、"活动页"、"临时页面"
  - Demo/原型："开发 xxx demo"、"做个示例"、"原型验证"
  - 实验性/个人项目："试试新技术"、"个人练习"
  - 用户明确说"不用走 Picasso"、"简单做一下"

  不确定时：询问用户"是否需要使用 HD 标准工作流（Picasso + git worktree + MR）？"
---

# HD Work Flow（强化版）

## 0) 入口决策
- 迭代模式：文档解析 → Picasso需求/迭代 → **worktree分支开发** → **提交MR审批** →（可选）发布
- 修改模式：已有迭代/MR，**worktree分支开发** → **提交MR审批** →（可选）发布

**核心约束：严禁在迭代分配的 target 分支直接修改提交，必须通过 worktree 分支开发并提交 MR 给用户审批。**

最小输入（只问缺失）：模式、文档、Picasso新建/复用、分支策略。
- 项目**不主动询问**，在文档解析后推测并让用户确认

---

## 1.5) 开发分支约束（重要）

**绝对禁止：直接在迭代分配的 target 分支上进行任何修改和提交。**

### 必须遵循的工作流程
1. **创建 worktree 开发分支**：基于 target 分支创建独立的 worktree 分支
2. **在 worktree 中开发**：所有代码修改、提交都在 worktree 分支进行
3. **提交 MR 审批**：通过 MR 将 worktree 分支合并到 target 分支，等待用户审批

### 禁止行为
- ❌ 直接 checkout 迭代分配的 target 分支并在其上修改
- ❌ 在 target 分支上直接 `git commit`
- ❌ 跳过 MR 流程直接推送代码到 target 分支

---

## 1.6) 迭代内问题修复规则

当用户需要对已有迭代进行问题修复或追加修改时，遵循以下规则：

### 检查现有 worktree
```bash
cd /Users/wuliangwei/WorkSpace/hd/<project>
git worktree list
```

- **如果之前的 worktree 分支仍在列表中**：
  - 直接进入该 worktree 目录继续开发
  - 无需创建新分支

- **如果 worktree 已清理**：
  - 基于迭代分配的 target branch 创建新的 worktree
  - **创建前必须先同步 base 分支最新更新**

### 同步 base 分支（必须）
在创建新 worktree 之前执行：
```bash
cd /Users/wuliangwei/WorkSpace/hd/<project>
git fetch origin <targetBranch>
git worktree add /Users/wuliangwei/WorkSpace/hd/_wt/<sourceBranch> origin/<targetBranch>
cd /Users/wuliangwei/WorkSpace/hd/_wt/<sourceBranch>
git switch -c <sourceBranch> || git switch <sourceBranch>
```

**关键原则**：始终基于最新的 base 分支创建开发分支，避免基于过时代码开发。

强制暂停：任意登录页或验证码。

---

## 1) 浏览器操作原语（必须）
1. `snapshot` 拿结构
2. 按可见文本定位目标
3. `act(click/type)` 操作
4. 再 `snapshot` 验证

### 弹窗铁律
- 点击主按钮后如弹窗出现，必须在弹窗内点“确定/提交”才算完成。
- 未达成功判据，不得向用户报“已完成”。

---

## 2) 功能流程

### A. 文档解析（迭代模式）
提取：需求名称、策划人、文档地址、一句话摘要。

**项目推测（关键步骤）：**
1. 阅读文档内容，识别涉及的功能模块、页面、API 或业务领域
2. 根据 `/Users/wuliangwei/WorkSpace/hd/` 下的项目目录，推测可能相关的项目（1个或多个）
3. 推测依据：
   - 文档中提到的系统/模块名称（如"校区管理"→hd-school-manage）
   - 页面路径或路由关键词
   - API 接口前缀
   - 涉及的业务线（招生/教务/财务等）
4. 向用户汇报推测结果："根据文档内容，推测涉及项目：A（原因）、B（原因），请确认"
5. 等待用户确认或修正

### B. Picasso 需求（创建/复用）
- 打开 https://picasso.haoduo.vip/home
- 需求列表检索同名需求
- 无则新建：需求名称/策划人/文档地址

### C. Picasso 迭代（创建/复用）
- 在需求下检查关联迭代
- 同项目迭代复用，否则新建
- **新建后刷新页面**（否则需求列表可能不显示刚创建的迭代）
- 记录迭代分支（target branch）

### D. 本地开发（worktree）

**⚠️ 强制要求：必须通过 worktree 分支开发，严禁直接在迭代分配的 target 分支上修改提交。**

```bash
cd /Users/wuliangwei/WorkSpace/hd/<project>
# 先同步 base 分支最新更新
git fetch origin <targetBranch>
# 基于最新 base 分支创建 worktree（创建独立的开发分支）
git worktree add /Users/wuliangwei/WorkSpace/hd/_wt/<sourceBranch> origin/<targetBranch>
cd /Users/wuliangwei/WorkSpace/hd/_wt/<sourceBranch>
git switch -c <sourceBranch> || git switch <sourceBranch>
# 开发后提交推送（提交到 worktree 分支，不是 target 分支）
git add -A
git commit -m "feat/fix: ..."
git push -u origin <sourceBranch>
```

**关键检查点：**
- ✅ 当前所在分支是 `<sourceBranch>`（worktree 分支）
- ✅ 提交推送到 `<sourceBranch>`
- ❌ 绝不在 `<targetBranch>` 上直接提交

**注意：** 如果是迭代内问题修复，先参考「1.6) 迭代内问题修复规则」检查现有 worktree。

### E. GitLab MR 创建
使用 `git push` 的 push options 直接创建 MR（无需打开浏览器）：

```bash
git push origin <sourceBranch> \
  -o merge_request.create \
  -o merge_request.target=<targetBranch> \
  -o merge_request.title="feat/fix: 简短描述" \
  -o merge_request.description="### 变更内容\n- xxx\n\n### 验证方式\n- 本地测试通过"
```

**重要：** `<targetBranch>` 是 worktree 创建时指定的上游分支（如 `main`、`master` 或迭代分配的系统分支），不是当前开发分支。

**选项说明：**
- `merge_request.create`：创建 MR
- `merge_request.target=<branch>`：指定目标分支（即 worktree 的上游分支）
- `merge_request.title`：MR 标题（遵循约定式提交格式）
- `merge_request.description`：MR 描述（支持 Markdown）

**纯推送（MR 已存在时）：**
```bash
git push origin <sourceBranch>
```

### F. Picasso 发布（QA）
详细步骤见：`references/publish-runbook.md`

### G. 清理
```bash
cd /Users/wuliangwei/WorkSpace/hd/<project>
git worktree list
git worktree remove /Users/wuliangwei/WorkSpace/hd/_wt/<sourceBranch>
```
禁止未经确认删除远端分支。

### H. 任务完成通知（必须）
**任务完成后必须向用户发送通知反馈，不能直接结束。**

通知内容应包含：
- **需求/迭代信息**：Picasso 需求名称、迭代号
- **开发信息**：worktree 分支名、MR 链接/状态
- **发布状态**：（如执行了发布）流水线状态、发布结果
- **后续建议**：如需测试验证、是否需要清理 worktree 等

**示例格式：**
```
✅ 任务完成

📋 Picasso: [需求名称] - 迭代 #[编号]
🔀 分支: <sourceBranch> → <targetBranch>
🔗 MR: [MR链接或已创建]
🚀 发布: [流水线状态或"未发布"]

💡 建议: 请前往 QA 环境验证，验证通过后通知可清理 worktree
```

---

## 3) 执行清单（每次必过）
执行前后按清单核对：`references/task-checklist.md`

---

## Resources
- `references/publish-runbook.md`：发布到 QA 的可执行步骤与成功判据
- `references/task-checklist.md`：每次任务防漏检查
- `references/git-worktree-cheatsheet.md`：worktree 常用命令

## 参考文档
- [GitLab Push Options](https://docs.gitlab.com/ee/topics/git/push_options.html)：使用 `git push -o` 直接创建 MR、设置标题/描述等

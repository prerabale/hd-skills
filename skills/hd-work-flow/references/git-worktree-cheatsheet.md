# git worktree cheatsheet

```bash
# 查看工作树
git worktree list

# 新建工作树（从目标分支）
git worktree add /path/to/_wt/<sourceBranch> <targetBranch>

# 进入并创建/切换分支
cd /path/to/_wt/<sourceBranch>
git switch -c <sourceBranch> || git switch <sourceBranch>

# 删除工作树（需在主仓库目录执行）
git worktree remove /path/to/_wt/<sourceBranch>
```

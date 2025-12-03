### Q1 当你想要修改之前commit所提交的message
更改的提交是：

1.最近的一次提交（即您当前 HEAD 指向的那个提交）。

2.更早的提交（历史记录中的任何一个提交）。

当想更改最近一次提交的消息 (HEAD)
这是最简单、最安全的方法，因为它只会修改您本地历史记录中的最后一个提交。

步骤
```bash
# 1. 执行 amend 命令
# --amend 标志会替换上次的提交，而不是创建一个新的提交
git commit --amend -m '你想要更改的message'
```
结果

执行上述命令后，Git 会打开您的默认文本编辑器，其中包含上次提交的消息。

相关编辑器使用的是Vim

编辑：在编辑器中修改提交消息。

保存并退出：保存文件并关闭编辑器。
推送到远程仓库

如果您这个需要修改的提交推送到了远程仓库，那么它的历史已经被改变了。您需要使用强制推送 (--force 或 -f) 来覆盖远程历史。
```bash
# 强制推送（覆盖远程仓库的上次提交）
git push --force-with-lease
# 推荐使用 --force-with-lease，比 -f 更安全一些
# 它会检查远程分支是否在您本地最后一次 fetch 之后有新的提交，如果有则拒绝推送。
```
2. 更改更早的提交的消息 (Interactive Rebase)
如果要更改历史记录中更早的提交，您需要使用 交互式变基 (Interactive Rebase)。

假设您要修改倒数第 N 个提交。
步骤

1.启动交互式变基：您需要变基到您想要修改的提交的前一个提交。 例如，如果要修改倒数第 3 个提交，则变基到 HEAD~3 的前一个提交，即 HEAD~4：

```bash
# 假设要修改历史记录中的倒数第 3 个提交
git rebase -i HEAD~4
```
2.编辑 Rebase To-Do 列表： Git 会打开一个编辑器，显示您即将处理的提交列表（从旧到新）。
```
pick <commit-hash> Commit message 1
pick <commit-hash> Commit message 2
pick <commit-hash> The commit I want to change <--- 假设是这一个
pick <commit-hash> Commit message 4

# Rebase commands:
# p, pick = use commit
# r, reword = use commit, but edit the commit message
# ...
```
3.将 pick 改为 reword： 找到您想要修改消息的那个提交，将其前面的 pick 命令改为 reword（或简写为 r）。
```
pick <commit-hash> Commit message 1
pick <commit-hash> Commit message 2
reword <commit-hash> The commit I want to change 
pick <commit-hash> Commit message 4
```
4.保存并关闭：保存文件并关闭编辑器。

5.修改消息： Git 会立即暂停并打开一个新的编辑器，其中包含您标记为 reword 的提交的旧消息。

* 编辑：修改提交消息。

* 保存并退出：保存并关闭编辑器。

6.Rebase 完成：变基操作会继续完成其余的提交。

推送到远程仓库

因为变基会重写历史（新的提交哈希），如果您已经将这些提交推送到了远程仓库，您同样需要使用强制推送。

```bash
# 强制推送，非常小心地使用
git push --force-with-lease
```
总结
场景	命令	是否需要强制推送	影响范围
最近一次提交 (HEAD)	git commit --amend	是 (如果已推送)	仅改变最近一个提交
历史记录中的提交	git rebase -i HEAD~N (用 reword)	是 (如果已推送)	重写从目标提交开始的历史记录
我建议您始终优先使用 git commit --amend，如果需要修改更早的提交，请确保您清楚交互式变基带来的历史重写影响。

您是想修改最近一次提交，还是更早的提交呢？
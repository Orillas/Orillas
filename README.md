## CLI Tools Learning Repository

这是一个用于记录、练习和整理我在学习 **命令行接口 (CLI) 工具** 知识时所创建脚本和笔记的仓库。主要关注 **Shell 脚本** 和 **Git 版本控制** 相关的操作与实践。

### 🚀 仓库内容概览

本仓库按照不同的 CLI 主题进行组织，方便查找和回顾。

| 文件夹/主题 | 描述 | 主要内容 |
| :--- | :--- | :--- |
| `shell/` | 🐧 **Bash/Zsh Shell 脚本**的练习与项目。 | 自动化任务、系统管理脚本、函数定义等。 |
| `Git/` | 🌳 **Git 版本控制**的高级与日常操作实践。 | Rebase、Cherry-pick、Submodule、Git Hook 示例等。 |
| `cli-tools-notes/` | 🛠️ 学习其他**常用 CLI 工具**的笔记和配置。 | `grep`, `awk`, `sed`, `tmux`, `ssh`, `curl` 等工具的配置和用法。 |
| `config-dotfiles/` | ⚙️ 我的 Shell 环境配置文件（`.bashrc`, `.zshrc`, `.gitconfig`）。 | 环境配置备份，别名 (Aliases)，自定义函数。 |

---

### 📘 Shell 学习重点

在 `shell-scripts/` 目录下，我主要学习和实践以下概念：

* **基础语法:** 变量、条件判断 (`if/elif/else`)、循环 (`for/while`)。
* **输入/输出:** 管道 (`|`)、重定向 (`>`, `>>`, `<`)、参数处理 (`$1`, `$@`)。
* **函数与模块化:** 脚本中的函数定义与调用。
* **实用脚本:** 文件批量重命名、日志分析、定时任务 (Cron)。

> 💡 **目标:** 能够编写健壮、可读性强且高效的 Shell 脚本，以实现日常任务的自动化。

### 🌲 Git 学习重点

在 `git-practices/` 目录下，我主要关注 Git 的高级用法和团队协作实践：

* **历史修改:** `git rebase` vs `git merge` 的使用场景。
* **工作区管理:** `git stash` 和多个分支间的切换与同步。
* **提交优化:** 使用 `git commit --amend` 和 `git rebase -i` 清理提交历史。
* **协作流程:** Pull Request/Merge Request 流程的理解和实践。

### 📚 推荐学习资源

以下是我在学习过程中参考的一些优秀资料：

1.  **Shell Scripting:**
    * [《Bash Guide for Beginners》](https://tldp.org/LDP/Bash-Beginners-Guide/html/) (可替换为您的实际参考资料)
    * [ShellCheck](https://www.shellcheck.net/)：一个帮助检查 Shell 脚本错误的工具。
2.  **Git:**
    * [《Pro Git》](https://git-scm.com/book/zh/v2) (中文版免费在线阅读)
    * [Learn Git Branching](https://learngitbranching.js.org/)：一个通过可视化交互学习 Git 分支的网站。

---

### 🤝 如何贡献（或自我监督）

虽然这是一个个人学习仓库，但我欢迎提出建议或指正代码中的错误。

1.  如果您发现我的脚本或笔记有误，请提交一个 **Issue**。
2.  如果您有更好的实现方式或优化建议，可以提交 **Pull Request**。

#### **作者信息**

* **GitHub:** Orillas
* **持续更新时间:** ～～随缘～～

---

### 许可证

本项目遵循 [MIT License](https://opensource.org/licenses/MIT)（您可以根据需要选择其他许可证）。

---

# GIT学习

[TOC]

## GIT BASICS

| 语法                          | 说明                                                         |
| ----------------------------- | ------------------------------------------------------------ |
| git init < directory >        | 在指定的目录下创建一个 新的git repo。<br>不带参数将在当前目录下创建一个git repo |
| git clone < repo >            | 克隆一个指定repo到本地。<br>指定repo可以是本地文件系统或者由HTTP或SSH指定的远程路径 |
| git config user.name < name > | 针对当前repo配置用户名。<br>使用--global参数参数将配置全局用户名 |
| git add < directory >         | 将指定目录的所有修改加入到下一次commit中。<br>把< directory >替换为< file >将添加指定文件的修改 |
| git commit -m "message"       | 提交暂存区的修改，使用指定的< message >作为提交信息          |
| git status                    | 显示那些文件已经被staged、未被staged以及未跟踪(untracked)。  |
| git log                       | 以缺省格式显示全部commit理室。<br>更多自定义参数参考后续部分 |

## GIT DIFF

| 语法              | 说明                               |
| ----------------- | ---------------------------------- |
| git diff          | 比较工作区和暂存区的修改           |
| git diff HEAD     | 比较工作区和上一次commit后的修改。 |
| git diff --cached | 比较暂存区和上一次commit后的修改   |

## UNDOING CHANGES

| 语法                  | 说明                                                         |
| --------------------- | ------------------------------------------------------------ |
| git revert < commit > | 对指定< commit >创建一个undo 的commit，并应用到当前分支      |
| git reset < file >    | 将< file >从暂存区移除，但保持工作区不变。<br />此操作不会修改工作区的任何和文件 |

## REWRITING GIT HISTORY

| 语法                            | 说明                                                         |
| ------------------------------- | ------------------------------------------------------------ |
| git commit -m "message" --amend | 将当前staged修改合并到最近一次的commit中                     |
| git rebase < base >             | 基于< base >对当前分支进行rebase。<br />< base >可以是commit、分支名称、tag或者相对于HEAD的commit |
| git reflog                      | 显示本地repo的所有commit日志                                 |

## GIT BRANCHES

| 语法                     | 说明                                                         |
| ------------------------ | ------------------------------------------------------------ |
| git branch               | 显示本地repo的所有分支                                       |
| git switch -c < branch > | 创建并切换到一个新的名为< branch >的分支。<br />去掉-c参数将切换到一个已有分支 |
| git merge < branch >     | 将指定< branach >分支合并到当前分支                          |

## REMOTE REPOSITORIES

| 语法                            | 说明                                                         |
| ------------------------------- | ------------------------------------------------------------ |
| git remote add < name > < url > | 添加一个新的远程连接。<br />添加后可使用< name >作为指定< url >远程连接的名称 |
| git fetch < remote > < branch > | 从指定< remote >抓取指定< branch >的所有commit到本地repo<br />去掉< branch>将抓取所有分支的修改 |
| git pull < remote >             | 从指定< remote >抓取所有分支的commit并立刻合并到本地repo     |
| git push < remote > < branch >  | 将本地指定< branch >推送到指定远程 < remote >。<br />如果远程没有对应分支，将自动在远程创建此分支 |

## GIT CONFIG

| 语法                                                    | 说明                                                         |
| ------------------------------------------------------- | ------------------------------------------------------------ |
| git config --global user.name < name >                  | 配置当前用户名。<br />使用--global参数将针对当前系统登陆用户生效 |
| git config --global user.email < email >                | 配置当前用户Email                                            |
| git config --global alias.< alias-name > < git commend> | 配置一个git的快捷方式                                        |
| git config --system core.editor < editor >              | 配置文本编辑器，例如vi,在必要时自动打开此文本编辑器。        |
| git config --global --edit                              | 打开房前用户的git 全局配置并编辑                             |

## GIT LOG

| 语法                           | 说明                                                         |
| ------------------------------ | ------------------------------------------------------------ |
| git log -< limit >             | 限制log的显示数量。<br />例如“git log -5”仅显示最新5条commit |
| git log --oneline              | 每行仅显示一条commit                                         |
| git log --author="< pattern >" | 按提交者名字搜索并显示commit                                 |
| git log --grep="< pattern >"   | 按指定内容搜索并显示commit                                   |
| git log --< file >             | 仅显示包含指定文件修改的commit                               |
| git log --graph                | 使用--graph参数显示图形化的branch信息                        |

## GIT RESET

| 语法                        | 说明                                                         |
| --------------------------- | ------------------------------------------------------------ |
| git reset                   | 移除所有暂存区的修改，但不会修改工作区                       |
| git reset --hard            | 移除所有暂存区的修改，并强制删除所有工作区的修改             |
| git reset < commit >        | 将当前分支回滚到指定< commit >，清除暂存区的修改，但保持工作区不变。 |
| git reset --hard < commit > | 将当前分支回滚到指定< commit >，清除暂存区的修改，并强制删除所有工作区的修改 |

## GIT REBASE

| 语法                   | 说明                         |
| ---------------------- | ---------------------------- |
| git rebase -i < base > | 以交互模式对当前分支做rebase |

## GIT PULL

| 语法                         | 说明                                                    |
| ---------------------------- | ------------------------------------------------------- |
| git pull --rebase < remote > | 抓取所有远程分支，并以rebase模式并入本地repo而不是merge |

## GIT PUSH

| 语法                        | 说明                                                         |
| --------------------------- | ------------------------------------------------------------ |
| git push < remote > --force | 将本地分支推送到远程。<br />不要使用force参数，除非你完全明白此操作的后果 |
| git push < remote > --tags  | 使用push命令并不会自动将本地tag推送到远程。<br />加上--tags 参数会将所有本地tag推送到远程 |

---
title: "参与贡献指南 "
date: 2021-01-09

---

# 贡献指南

> 作者：Plato-W

> 审核：AKA二夕


前段时间一直有小伙伴在询问具体该如何参与项目中来，所以在借鉴了一些开源项目指南的基础上，编写了本文，如果感觉有不足之处，欢迎大家来适当补充。

这篇贡献指南会指导你如何为 `KO——CSP` 贡献一份自己的力量，请在要提 `Issue` 或者 `Pull request` 之前花几分钟来阅读一遍这篇指南。

-    [提交 Issue](https://github.com/OS-EDU/KO--CSP/issues)
-    [提交 Pull Request](https://github.com/OS-EDU/KO--CSP/pulls)

##  提交 issue

有任何疑问，欢迎[提交 Issue](https://github.com/OS-EDU/KO--CSP/issues)。提交 issue 之前:

-    避免提交重复的 issue，在提交之前搜索现有的 issue。
-    确定 issue 的类型，并在标题或内容中标明。如 `add questions`, `bug`, `documentation`, `discussion`, `help wanted`等。[查看所有标签](https://github.com/OS-EDU/KO--CSP/labels)。

##  提交 Pull Request

如果你准备提交 Pull Request ，可参考以下流程：

### 1. 认领 issue

所有的题目都会建立一个对应的issue，可以选择在 [Issue 列表](https://github.com/Practice-Dream/KO--CSP/issues) 中挑选任务，然后在该 `issue` 下回复一下自己简单的解题思路，表明你将认领该 issue，如果发现issue已被认领或者closed，但是还有不同的解法，可以自己new issue，issue的标题要表明对应的题目编号。

>    可以在 Issue 流程相关中找到更多与 `Issue` 流程相关的信息。

### 2. 克隆仓库

访问 [KO--CSP](https://github.com/OS-EDU/KO--CSP) 仓库的主页，并 `Fork` 到自己的账号下。

回到自己的 `GitHub` 主页，并找到刚刚 `Fork` 过来的仓库，进入仓库主页, 将该仓库 `clone` 到本地，如：

```shell
# 将下面的 XXX 替换成你自己的用户名
$ git clone git@github.com:XXX/KO--CSP.git
$ cd KO--CSP
```

### 3. 新建 `branch`

>    非紧急修复，不建议在 `main` 分支进行开发修改。

根据该分支的用途，起一个恰当的分支名称，新建分支，如：

```shell
$ git checkout -b doc/add-contributing-guide
```

### 5. 修改内容，并提交

对相应文件做出修改，修改完成后，提交：

```shell
$ git add .
$ git commit -sm "docs: add contributing guide"
```

提交时尽量参考 [angular 提交规范](https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#-git-commit-guidelines)：

(1) 用一句话清楚的描述这次提交做了什么。

(2) 关联相关 `issue`，如 `fix #1` 、`close #2`、`#3`

### 6. 同步上游仓库变更

同步上游仓库变更，因为可能有其他人先于你提交到上游仓库，防止冲突：

```bash
$ git remote add upstream git@github.com:OS-EDU/KO--CSP.git
$ git fetch upstream
```

若上游仓库有变更，需要先进行 `rebase`:

```bash
$ git rebase upstream/main
```

如果发生冲突，你需要手动修改冲突文件，然后:

```shell
$ git add my-fix-file
$ git rebase --continue
```

### 7. 推送新分支到自己的远程仓库

```shell
$ git push -f origin your-branch-name:your-branch-name
```

### 8. 提交 `Pull Request`

在自己仓库的页面上提 `Pull Request` 到上游仓库 `OS-EDU
/KO--CSP`。

其他人将会对你的 `Pull Request` 进行`review`， `review` 之后，如果需要再进行更改，就修改相关内容，然后执行以下操作，该 PR 将会自动同步该 `commit` 。

```shell
$ git add .
$ git commit --amend
$ git push -f origin your-branch-name
```

### 9. 代码合并之后，你可以：

-    删除远程分支:

     ```shell
     $ git push origin --delete branch-name
     ```

-    切回到 `main` 分支:

     ```shell
     $ git checkout master -f
     ```

-    删除本地分支(可选):

     ```shell
     $ git branch -D my-fix-branch
     ```

-    保持本地 `main` 分支与上游分支同步:

     ```shell
     $ git pull --ff upstream main
     ```

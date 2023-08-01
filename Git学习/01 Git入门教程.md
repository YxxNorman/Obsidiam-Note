# Git入门教程
## 初始化设置
```
$ git config --global user.name "Your name"    # 配置用户名
$ git config --global user.email "norman@qq.com"    # 配置邮箱
```
## 创建仓库
创建仓库有两种方法，一种方法是在本地直接创建仓库，另一种方法是克隆远程仓库。
- 本地创建仓库
```
$ git init <project-name>    # <project-name>为空则在当前文件夹创建
```
- 克隆远程仓库
```
$ git clone <url>
```
## 工作区域
Git 分为四个区域：
- 工作区（Working Directory）：就是在电脑⾥能实际看到的⽬录。
- 暂存区（Stage/Index）：暂存区也叫索引，⽤来临时存放未提交的内容，⼀般在.git⽬录下的index中。
- 本地仓库（Repository）：Git在本地的版本库，仓库信息存储在.git这个隐藏⽬录中。
- 远程仓库（Remote Repository）：托管在远程服务器上的仓库。常⽤的有GitHub、GitLab、Gitee。
文件状态：
- main/master : 默认主分支
- Origin : 默认远程仓库
- HEAD : 当前版本指针
- HEAD^ : 上一个版本
- HEAD~ : 上四个版本
## 添加与提交文件
在工作区新建的文件需要先添加至暂存区，再进行提交至本地仓库。
添加至暂存区：
```
$ git add <filename>
$ git add .    # 添加所有文件
```
提交至本地仓库：
```
$ git commit -m "message"    # message是填写每次提交的信息
```
因此，文件有三种不同状态：
- 未跟踪（Untrack）：新建文件的状态
- 未修改（Unmodified）：被Git管理起来，但是未被修改的文件
- 已修改（Modified）：已经修改过的文件，还未暂存
- 已暂存（Staged）：修改后已保存到暂存区的文件
- 已提交（Committed）：已经提交到本地仓库的文件
查看仓库的状态：
```
$ git status
```
查看仓库的提交记录：
```
$ git log
$ git log --oneline    # 显示简洁模式
```
## 撤销和恢复文件
移动文件位置：
```
$ git mv <file> <new-file>
```
删除文件：
```
$ git rm <file>    # 删除工作区和暂存区的文件
$ git rm -f <file>    # 强制删除工作区和暂存区已修改过的文件
$ git rm --cached <file>    # 删除暂存区的文件，但保留工作区

```
重置当前HEAD分支到某一提交版本，并且删除之后的所有提交：
```
$ git reset --soft <commit-id>    # 保留工作区和暂存区文件
$ git reset --hard <commit-id>    # 重置工作区和暂存区文件
$ git reset --mixed <commit-id>   # 重置暂存区文件，保留工作区
```
## 比较差异
```
$ git diff    # 比较工作区与暂存区的差异
$ git diff HEAD    # 比较工作区+暂存区与本地仓库的差异
$ git diff HEAD --cached/--staged    # 比较暂存区与本地仓库的差异
$ git diff <commit-id> <commit-id>   # 比较提交版本之间的差异
$ git diff HEAD~ HEAD    # 比较上一个提交版本与当前版本之间的差异
$ git diff <branch_name> <branch_name>  # 比较分支之间的差异
```
## .gitignore忽略文件
.gitignore文件的匹配规则：
- 空行或者以`#`开头的行会被Git忽略。一般空行用于可读性的分隔，`#`一般用作注释
- 星号`*`通配任意个字符
- 问号`?`匹配单个字符
- 中括号`[]`表示匹配列表中的单个字符，比如：`[abc]`表示a/b/c
- 两个星号`**`表示匹配任意的中间目录
- 中括号可以使用短中线连接，比如：`[0-9]`表示任意一位数字，`[a-z]`表示任意一位小写字母感叹号
- `!`表示取反
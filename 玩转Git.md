# 玩转Git

## 第 1 章 Git概述

​		Git 是一个免费的、开源的==分布式版本控制系统==，可以快速高效的处理从小型到大型的各种项目。

### 1.1 Git 工作机制

![1636292730774](C:\Users\蒋金林\AppData\Roaming\Typora\typora-user-images\1636292730774.png)

### 1.2 Git 和代码托管中心

代码托管中心是基于网络服务器的远程代码仓库，一般我们简称为==远程库==

* **局域网**
  * GitLab
* **互联网**
  * GitHub（外网）
  * Gitee 码云（国内网站）

## 第 2 章 Git 安装

Git官网下载Git：https://git-scm.com/

双击其可执行程序，一直点下一步安装Git

## 第 3 章 Git 常用命令

| 命令名称                             | 作用           |
| ------------------------------------ | -------------- |
| git config --global user.name 用户名 | 设置用户签名   |
| git config --global user.name 邮箱   | 设置用户签名   |
| ==git init==                         | 初始化本地库   |
| ==git status==                       | 查看本地库状态 |
| ==git add 文件名==                   | 添加到暂存区   |
| ==git commit -m “日志信息” 文件名==  | 提交到本地库   |
| ==git reflog==                       | 查看历史记录   |
| ==git reset --hard 版本号==          | 版本穿梭       |

### 3.1 设置用户签名

**1）基本语法**

git config --global user.name 用户名

git config --global user.email 邮箱

说明：

​		签名的作用是区分不同操作者身份。用户的签名信息在每一个版本的提交信息中都可以看到，以此确认本次提交是谁做的。==Git 首次安装必须设置一下用户签名，否则无法提交代码。==

​		注意：这里设置用户签名和将来登录 GitHub（或其他代码托管中心）的账号没有任何关系

### 3.2 初始化本地库

**1）基本语法**

git init

效果：生成一个 .git目录

### 3.3 查看本地库状态

**1）基本语法**

git status

#### 3.3.1 首次查看（工作区没有任何文件）

git status

![1636297042922](C:\Users\蒋金林\AppData\Roaming\Typora\typora-user-images\1636297042922.png)

#### 3.3.2 新增文件后查看（检测到未追踪的文件）

git status

![1636297159878](C:\Users\蒋金林\AppData\Roaming\Typora\typora-user-images\1636297159878.png)

### 3.4 添加暂存区

#### 3.4.1 将工作区的文件添加到暂存区

![1636297285382](C:\Users\蒋金林\AppData\Roaming\Typora\typora-user-images\1636297285382.png)

#### 3.4.2 查看状态（检测到暂存区有新文件）

![1636297354910](C:\Users\蒋金林\AppData\Roaming\Typora\typora-user-images\1636297354910.png)

### 3.5 提交本地库

#### 3.5.1 将暂存区的文件提交到本地库

**1）基本语法**、

git commit -m "日志信息" 文件名

![1636298122106](C:\Users\蒋金林\AppData\Roaming\Typora\typora-user-images\1636298122106.png)

#### 3.5.2 查看状态（没有文件需要提交）

![1636298144800](C:\Users\蒋金林\AppData\Roaming\Typora\typora-user-images\1636298144800.png)

### 3.6 历史版本

#### 3.6.1 查看历史版本

**1）基本语法**

git reflog 查看版本信息

git log 查看版本详细信息

#### 3.6.1 版本穿梭

**1）基本语法**

git reset --hard 版本号

## 第 4 章 Git分支操作

### 4.1 分支的操作

| 命令名称            | 作用                       |
| ------------------- | -------------------------- |
| git branch 分支名   | 创建分支                   |
| git branch -v       | 查看分支                   |
| git checkout 分支名 | 切换分支                   |
| git merge 分支名    | 把指定的分支合并到当前分支 |

#### 4.1.1 查看分支

**1）基本语法**

git branch -v

![1636382138588](C:\Users\蒋金林\AppData\Roaming\Typora\typora-user-images\1636382138588.png)

#### 4.1.2 创建分支

**1）基本语法**

git branch 分支名

![1636382432869](C:\Users\蒋金林\AppData\Roaming\Typora\typora-user-images\1636382432869.png)

#### 4.1.3 切换分支

**1）基本语法**

git checkout 分支名

![1636382465222](C:\Users\蒋金林\AppData\Roaming\Typora\typora-user-images\1636382465222.png)

#### 4.1.4 合并分支

**1）基本语法**

git merge 分支名

#### 4.1.5 产生冲突

冲突产生的表现：后面状态为==MERGING==

冲突产生的原因：

​		合并分支时，两个分支在==同一个文件的同一个位置==有两套完全不同的修改。Git 无法替我们决定使用哪一个。必须人为决定新代码内容。

#### 4.1.6 解决冲突

1）编辑有冲突的文件，删除特殊符号，决定要使用的内容

特殊符号：==<<<<<<<HEAD== 当前分支的代码 ========================= 合并过来的代码 ==>>>>>> 分支名==

2）添加到暂存区

git add 文件名

3）执行提交（注意：此时使用 git commit 命令时==不能带文件名==）

## 第 5 章 Git 团队协作机制

### 5.1 团队内协作

![1636384002010](C:\Users\蒋金林\AppData\Roaming\Typora\typora-user-images\1636384002010.png)

### 5.2 跨团队协作

![1636384041211](C:\Users\蒋金林\AppData\Roaming\Typora\typora-user-images\1636384041211.png)

## 第 6 章 GitHub操作

==GitHub 网址：==[https://github.com/](https://github.com/)

### 6.1 创建远程仓库

![1636385827649](C:\Users\蒋金林\AppData\Roaming\Typora\typora-user-images\1636385827649.png)

![1636385869112](C:\Users\蒋金林\AppData\Roaming\Typora\typora-user-images\1636385869112.png)

### 6.2 远程仓库操作

| 命令名称                           | 作用                                                     |
| ---------------------------------- | -------------------------------------------------------- |
| git remote -v                      | 查看当前所有远程地址别名                                 |
| git remote add 别名 远程地址       | 起别名                                                   |
| git push 别名 分支                 | 推送本地分支上的内容到远程仓库                           |
| git clone 远程地址                 | 将远程仓库的内容克隆到本地                               |
| git pull 远程库地址别名 远程分支名 | 将远程仓库对于分支最新内容拉下来后与当前本地分支直接合并 |


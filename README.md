### Git 简史
Linux在 1991-2002年用的是BitKeeper,后面到2005年, BitKeeper 的商业公司同 Linux 内核开源社区的合作关系结束，他们收回了 Linux 内核社区免费使用 BitKeeper 的权力。
这就迫使 Linux 开源社区（特别是 Linux 的缔造者 Linus Torvalds）基于使用 BitKeeper 时的经验教训，开发出自己的版本系统 git

Git是一个分布式版本控制系统（DVCS）

### 快照（Snapshots）与记录变更(Differences)

Git与SVN最大的差别在于它们如何处理数据：
- SVN等大多数版本控制系统存储的数据是一系列记录项目文件变更的文件
- Git存储的数据则更像是一个微型文件系统的一系列快照，即快照流

每次提交或保存当前项目状态，Git都会生成一个当前所有文件状态的快照，并存储一个对该快照的引用；而且文件没有发生变化时

### 初始配置

Git 自带一个 git config 的工具来帮助设置控制 Git 外观和行为的配置变量。 这些变量存储在三个不同的位
置

- 当前使用仓库的 Git 目录中的 config 文件(就是 .git/config):针对该仓库
- ~/.gitconfig 或 ~/.config/git/config 文件:只针对当前用户。 可以传递 --global 选项让 Git
  读写此文件
- /etc/gitconfig 文件: 包含系统上每一个用户及他们仓库的通用配置。 如果使用带有 --system 选项的
 git config 时,它会从此文件读写配置变量

如果想要检查你的配置,可以使用 git config --list(-l) 命令来列出所有 Git 当时能找到的配置。

```
$ git config --list
user.name=zhengwu
user.email=zhengwu@globalegrow.com
core.autocrlf=input
```

要想获得 config 命令的手册,执行

```
$ git help config
```

### 基本命令

```
$ git init
$ git add LICENSE
$ git commit -m 'initial project version'
$ git push orign master
$ git clone https://github.com/libgit2/libgit2 // 支持https:// , git://或者SSH,比如 user@server:path/to/repo.git
$ git status //检查当前文件状态
```

分支
```
$ git checkout -b hotfix//切换到hotfix分支
$ git branch//查看当前分支
$ git branch -d hotfix //删除分支
```

合并分支的代码

```
$ git checkout master
$ git merge hotfix
```

创建tag
```
$ git tag -a v1.0 -m 'my version' //创建附注标签
$ git show v1.0 //看到标签信息与对应的提交信息
$ git tag v1.0-lw //创建轻量标签
```

后期打tag
```
$ git log --pretty=oneline//查看日志
$ git tag -a v1.2 9fceb02//指定提交的校验和(或部分校验和)
```

Note: 默认情况下,git push 命令并不会传送标签到远程仓库服务器上。 在创建完标签后你必须显式地推送标签到
      共享服务器上。 这个过程就像共享远程分支一样 - 你可以运行 git push origin [tagname]。

# GitTest
git 相关操作

master change
testing


branch commit

add test branch

add 

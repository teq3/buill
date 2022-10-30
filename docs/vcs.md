🐌 `VCS`相关脚本
====================================

> 你会发现这些脚本都是`svn`分支相关的操作。
>
> 个人在使用`Git`的过程中（7年+），并没有发现有对应脚本的需求（侧面反映出`Git`的优秀）。  
> 原因：`Git`的概念模型一等公民支持分支，切换分支是件很简单且统一的事，而`svn`不得不涉及仓库的`URL`（不统一简单）。
>
> 我已经在自己的开发机上卸载了`svn`，没有需求场景也没理由再用了。 😛
>
> 使用更现代的`Git`吧！ 💥

1. [swtrunk](#-swtrunk)  
    自动`svn`工作目录从分支（`branches`）切换到主干（`trunk`）。  
    PS： `Git`对应的是`git checkout master`，如果你使用了`oh-my-zsh`，已经有对应的别名加速了：`gcm`。
1. [svn-merge-stop-on-copy](#-svn-merge-stop-on-copy)  
    把指定的远程分支从刚新建分支以来的修改合并到本地`svn`目录或是另一个远程分支。  
    PS：`Git`的合并很直接简单，`git merge branch-foo`，也更智能（没有树冲突一说）。
1. [cp-svn-url](#-cp-svn-url)  
    拷贝当前`svn`目录对应的远程分支到系统的粘贴板，省去`CTRL+C`操作。  
    PS：`Git`分支不需要`URL`来引用，没有这个脚本的需求，直接给个分支名就好了。

🍺 [swtrunk](../legacy-bin/swtrunk)
----------------------

`svn`工作目录从分支（`branches`）切换到主干（`trunk`）。  
支持`Linux`、`Mac`、`Windows`（`cygwin`、`MSSYS`）。

命令以`svn`的标准目录命名约定来识别分支和主干。
即，分支在目录`branches`下，主干在目录`trunk`下。
示例：

- 分支： <http://www.foo.com/project1/branches/feature1>
- 主干： <http://www.foo.com/project1/trunk>

### 用法

```bash
swtrunk # 缺省使用当前目录作为svn工作目录
swtrunk path/to/svn/work/directory
swtrunk path/to/svn/work/directory1 /path/to/svn/work/directory2 # svn工作目录个数不限制
```

### 示例

```bash
$ swtrunk
# <svn sw output...>
svn work dir . switch from https://www.foo.com/project1/branches/feature1 to https://www.foo.com/project1/trunk !

$ swtrunk /path/to/svn/work/dir
# <svn sw output...>
svn work dir /path/to/svn/work/dir switch from https://www.foo.com/project1/branches/feature1 to https://www.foo.com/project1/trunk !

$ swtrunk /path/to/svn/work/dir1 /path/to/svn/work/dir2
# <svn sw output...>
svn work dir /path/to/svn/work/dir1 switch from https://www.foo.com/project1/branches/feature1 to https://www.foo.com/project1/trunk !
# <svn sw output...>
svn work dir /path/to/svn/work/dir2 switch from https://www.foo.com/project2/branches/feature1 to https://www.foo.com/project2/trunk !
```

🍺 [svn-merge-stop-on-copy](../legacy-bin/svn-merge-stop-on-copy)
----------------------

把指定的远程分支从刚新建分支以来的修改合并到本地`svn`目录或是另一个远程分支。  
支持`Linux`、`Mac`、`Windows`（`cygwin`、`MSSYS`）。

### 用法

```bash
svn-merge-stop-on-copy <来源的远程分支> # 合并当前本地svn目录
svn-merge-stop-on-copy <来源的远程分支> <目标本地svn目录>
svn-merge-stop-on-copy <来源的远程分支> <目标远程分支>
```

### 示例

```bash
svn-merge-stop-on-copy https://www.foo.com/project1/branches/feature1 # 缺省使用当前目录作为svn工作目录
svn-merge-stop-on-copy https://www.foo.com/project1/branches/feature1 /path/to/svn/work/directory
svn-merge-stop-on-copy https://www.foo.com/project1/branches/feature1 https://www.foo.com/project1/branches/feature2
```

### 贡献者

[姜太公](https://github.com/jzwlqx)提供此脚本。

🍺 [cp-svn-url](../legacy-bin/cp-svn-url)
----------------------

拷贝当前`svn`目录对应的远程分支到系统的粘贴板，省去`CTRL+C`操作。  
支持`Linux`、`Mac`、`Windows`（`cygwin`、`MSSYS`）。

### 用法

```bash
cp-svn-url # 缺省使用当前目录作为svn工作目录
cp-svn-url /path/to/svn/work/directory
```

### 示例

```bash
$ cp-svn-url
https://www.foo.com/project1/branches/feature1 copied!
```

### 贡献者

[ivanzhangwb](https://github.com/ivanzhangwb)提供此脚本。

### 参考资料

[拷贝复制命令行输出放在系统剪贴板上](http://oldratlee.github.io/post/2012-12-23/command-output-to-clip)，给出了不同系统可用命令。

# 第十讲 ：Git中的分支[重要]

## Git分支

![截屏2022-05-01 16.27.39](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011627456.png)

- 在版本控制过程中，同时推进多个任务，为每个任务，我们就可以创建每个任务的单独分支
- 使用分支意味着程序员可以把自己的工作从开发主线上分离开来，开发自己分支的时候，不会影响主线分支的运行
- 对于初学者而言，分支可以简单理解为副本，一个分支就是一个单独的副本

###  分支的操作

| 命令名称            | 作用                         |
| ------------------- | ---------------------------- |
| git branch 分支名   | 创建分支                     |
| git branch -v       | 查看分支                     |
| git checkout 分支名 | 切换分支                     |
| git merge 分支名    | 把指定的分支合并到当前分支上 |

分支在GIT中相对较难，分支就是科幻电影里面的平行宇宙，如果两个平行宇宙互不干扰，那对现在的你也没啥影响。**不过，在某个时间点，两个平行宇宙合并了，我们就需要处理一些问题了！**

![图片](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011136789.png)

![图片](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011136425.png)

git分支中常用指令：

```

# 列出所有本地分支
git branch

# 列出所有远程分支
git branch -r

# 新建一个分支，但依然停留在当前分支
git branch [branch-name]

# 新建一个分支，并切换到该分支
git checkout -b [branch]

# 合并指定分支到当前分支
$ git merge [branch]

# 删除分支
$ git branch -d [branch-name]

# 删除远程分支
$ git push origin --delete [branch-name]
$ git branch -dr [remote/branch]
```

DEA中操作

![图片](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011138996.png)

如果同一个文件在合并分支时都被修改了则会引起冲突：解决的办法是我们可以修改冲突文件后重新提交！选择要保留他的代码还是你的代码！

**master主分支应该非常稳定，用来发布新版本，一般情况下不允许在上面工作，工作一般情况下在新建的dev分支上工作，工作完后，比如上要发布，或者说dev分支代码稳定后可以合并到主分支master上来。**

### 查看分支

基本语法：`git branch -v`

![img](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011207795.png)

### 创建分支

基本语法：`git branch 分支名`

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011208477.png)

### 切换分支

基本语法:`git checkout 分支名`

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011208846.png)

### 修改分支 ：在分支上进行操作

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011209217.png)

### 合并分支

基本语法：`git merge 分支名`

##### ①正常合并不冲突

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011209785.png)

##### ②合并产生冲突
冲突产生的原因：

* 合并分支时，两个分支在同一个文件的同一个位置有两套完全不同的修改。
* 有两套完全不同的修改。 Git无法替我们决定使用哪一个。必须 人为决定新代码内容。
  **例如，我们首先在 master 分支的倒数第二行进行修改，并将其添加到暂存区，再提交到本地库**

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011210485.png)

**接着，我们去 hot-fix 分支的倒数第一行进行修改，并将其添加到暂存区，再提交到本地库**

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011211054.png)

**之后我们在 master 分支上合并 hot-fix 分支，发现产生冲突**

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011211268.png)

> 解决冲突

1. 编辑有冲突的文件，删除特殊符号，决定要使用的内容

   特殊符号：`<<<<<< HEAD` 当前分支的代码 `=======` 合并过来的代码 `>>>>>>>hot-fix`

   ![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011213597.png)

   ![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011213494.png)

**删除完成之后保存，再次添加到暂存区，并再次提交到本地库(注意：此时使用 git commit 命令时候不能带文件名)**

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011215259.png)




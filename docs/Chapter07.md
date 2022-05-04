# 第七讲 ：Git文件操作



## 文件的四种状态

**版本控制就是对文件的版本控制，要对文件进行修改、提交等操作，首先要知道文件当前在什么状态，不然可能会提交了现在还不想提交的文件，或者要提交的文件没提交上。**

- **Untracked**: 未跟踪, 此文件在文件夹中, 但并没有加入到git库, 不参与版本控制. 通过git add 状态变为Staged.
- **Unmodify**: 文件已经入库, 未修改, 即版本库中的文件快照内容与文件夹中完全一致. 这种类型的文件有两种去处, 如果它被修改, 而变为Modified. 如果使用git rm移出版本库, 则成为Untracked文件
- **Modified**: 文件已修改, 仅仅是修改, 并没有进行其他的操作. 这个文件也有两个去处, 通过git add可进入暂存staged状态, 使用git checkout 则丢弃修改过, 返回到unmodify状态, 这个git checkout即从库中取出文件, 覆盖当前修改 !
- **Staged**: 暂存状态. 执行git commit则将修改同步到库中, 这时库中的文件和本地文件又变为一致, 文件为Unmodify状态. **执行git reset HEAD filename取消暂存, 文件状态为Modified**

![截屏2022-05-01 11.50.33](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011150711.png)

### 添加暂存区：将工作区的文件添加到暂存区
基本语法：```git add 文件名```

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011200048.png)

### 提交本地库: 将工作区的文件提交到本地库

基本语法：```git commit -m "日志信息" 文件名```

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011201795.png)

### 修改文件

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011202846.png)

### 历史版本
基本语法：

```git reflog 查看版本信息 , git log 查看版本详细信息```

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011203524.png)

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011203378.png)


但是我们工作区的 hello.txt 始终只有一个文件存在

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011204714.png)

#### 版本穿梭
语法：```git reset --hard 版本号```

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011205080.png)



### 切换版本原理[重要]
**Git 切换版本，底层其实是移动的HEAD 指针，**具体原理如下图所示

HEAD 指针指向 master 分支，master分支指向 first 版本，

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011205676.png)

之后有了 second 版本，master 指针指向 second 版本

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011205271.png)

之后有了third 版本，master 指针指向 third 版本

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011205606.png)

如果我们想穿越回去，只需要让 master 指针指向 first 版本或者 second 版本

## 查看文件状态

上面说文件有4种状态，通过如下命令可以查看到文件的状态：

```git

#查看指定文件状态
git status [filename]

#查看所有文件状态
git status

# git add .                  添加所有文件到暂存区
# git commit -m "消息内容"    提交暂存区中的内容到本地仓库 -m 提交信息
```

## 忽略文件

有些时候我们不想把某些文件纳入版本控制中，比如数据库文件，临时文件，设计文件等

在主目录下建立".gitignore"文件，此文件有如下规则：

1. 忽略文件中的空行或以井号（#）开始的行将会被忽略。
2. 可以使用Linux通配符。例如：星号（*）代表任意多个字符，问号（？）代表一个字符，方括号（[abc]）代表可选字符范围，大括号（{string1,string2,...}）代表可选的字符串等。
3. 如果名称的最前面有一个感叹号（!），表示例外规则，将不被忽略。
4. 如果名称的最前面是一个路径分隔符（/），表示要忽略的文件在此目录下，而子目录中的文件不忽略。
5. 如果名称的最后面是一个路径分隔符（/），表示要忽略的是此目录下该名称的子目录，而非文件（默认文件或目录都忽略）。

```java
#为注释
*.txt        #忽略所有 .txt结尾的文件,这样的话上传就不会被选中！
!lib.txt     #但lib.txt除外
/temp        #仅忽略项目根目录下的TODO文件,不包括其它目录temp
build/       #忽略build/目录下的所有文件
doc/*.txt    #会忽略 doc/notes.txt 但不包括 doc/server/arch.txt
```


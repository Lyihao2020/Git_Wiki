# 第九讲 ：IDEA集成Git操作

## IDEA与Git的基础

1、新建项目，绑定git

![图片](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011133614.jpeg)

注意观察idea中的变化

![图片](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011135985.png)

2、修改文件，使用IDEA操作git。

- 添加到暂存区
- commit 提交
- push到远程仓库

3、提交测试

![图片](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011136190.jpeg)

---

## IDEA的Git忽略文件配置

我们的[Eclipse](https://so.csdn.net/so/search?q=Eclipse&spm=1001.2101.3001.7020) 、IDEA都会生成一些无关文件，如图

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011523984.png)

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011523470.png)

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011524442.png)

我们之所以要忽略他们，是因为他们与项目的实际功能无关，不参与服务器上部署运行。如何忽略他们？

1. **在用户家(C/User/用户名) 下创建 `git.ignore`**

   ```
   # Compiled class file
   *.class
   
   # Log file
   *.log
   
   # BlueJ files
   *.ctxt
   
   # Mobile Tools for Java (
   .mtj.
   
   # Package Files
   *.jar
   *.war
   *.nar
   *.ear
   *.zip
   *.tar.gz
   *.rar
   
   # virtual machine crash logs, see
   http://www.java.com/en/download/help/error_hotspot.xml
   hs_err_pid*
   
   .classpath
   .project
   .settings
   target
   .idea
   *.iml
   
   以下可见 Chapter07.md 
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

   ![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011524776.png)

2. **在 .gitconfig 文件中引用忽略配置文件(.gitconfig 在家目录中)**

   ```
   [user]
   	name = Augenestern
   	email = .....@qq.com
   [core]
   	excludesfile = C:/Users/Augenestern/git.ignore
   
   ```

   ![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011527375.png)

3. **在 IDEA 里面定位**

   ![](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011527933.png)

----

## IDEA初始化本地库

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011528001.png)

默认创建的 git 仓库就是我们打开的项目所在的目录，我们添加了 git 仓库之后

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011528519.png)

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011528950.png)

添加到暂存区就变为了绿色，我们可以写些代码，然后将 project 添加到暂存区

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011528651.png)

我们添加到暂存区，再接着进行提交到本地库

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011529743.png)

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011529034.png)

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011529980.png)

## 切换版本

我们修改 GitTest 中的代码，再次提交到本地库

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011530475.png)

在IDEA的左下角，点击 Git，然后点击 Log查看版本，右键选择要切换的版本，然后在菜单里点击 Checkout Revision

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011530840.png)

---

## 创建分支

```右键项目 -> Git -> Branches```

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011530229.png)

在弹出的Git Branches框里 点击 New Branch按钮。

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011531537.png)

填写分支名称

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011531270.png)

然后再 IDEA的右下角看到 hot-fix，说明分支创建成功，并且当前已经切换成 hot-fix分支

![img](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011532467.png)

---

## 切换分支

在IDEA窗口的右下角，切换到 master分支 

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011532722.png)

---

## 合并分支

在IDEA窗口的右下角，将 hot-fix分支合并到当前 master分支

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011532029.png)

**如果代码没有冲突，分支直接合并成功，分支合并成功以后，代码自动提交，无需手动提交本地库**

----

## 合并分支冲突

如图所示，如果master分支和 hot-fix分支都修改了代码，在合并分支的时候就会发生冲突

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011533216.png)

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011533417.png)

我们现在站在master分支上合并 hot-fix分支，就会发生代码冲突。

**点击 Conflicts框里的 Merge按钮，进行手动合并代码**

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011534538.png)

**手动合并完代码以后，点击右下角的 Apply按钮。代码冲突解决，自动提交本地库**

---

## IDEA集成Github

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011536810.png)

Token在哪呢？我们在 Github 点击``` Settings -> Develop Settings```

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011536887.png)

**下面的Token 的 Expiration 如果到期了就需要重新设置**

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011536206.png)

点击 Generate token

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011537375.png)

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011537365.png)

---

## 分享项目到Github

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011538999.png)

这其实就是创建远程库，名字，是否私有，描述等

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011538294.png)

---

## push推送本地库到远程库

右键点击项目，可以将当前分支的内容 push 到 GitHub的远程仓库中 

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011538548.png)

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011539780.png)

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011539222.png)

---

## pull拉取远程库到本地库
注意：push是将本地库代码推送到远程库，如果本地库代码跟远程库代码版本不一致，push的操作是会被拒绝的。也就是说， 要想 push成功，一定要保证本地 库的版本要比远程库的版本高！ **因此一个成熟的程序员在动手改本地代码之前，一定会先检查下远程库跟本地代码的区别**！如果本地的代码版本已经落后，切记要先 pull拉取一下远程库的代码，将本地代码更新到最新以后，然后再修改，提交，推送！

* 右键点击项目，可以将远程仓库的内容pull到本地仓库

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011540453.png)

* 注意：pull是拉取远端仓库代码到本地，如果远程库代码和本地库代码不一致，会自动合并，如果自动合并失败，还会涉及到手动解决冲突的问题。

---

## clone克隆远程库到本地库

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011541892.png)

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011541510.png)

----

#IDEA集成Gitee

## IDEA安装码云插件
Idea 默认不带码云插件，我们第一步要安装 Gitee插件。

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011543150.png)

安装完成重启 IDEA 即可

**Idea连接码云和连接 GitHub几乎一样**，首先在 Idea里面创建一个工程，初始化 git工程，然后将代码添加到暂存区，提交到本地库。

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011543287.png)

## 分享项目到Gitee

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011543725.png)

## push推送到码云远程库

当然我们也可以自己在码云Gitee上创建远程库，然后获取到远程库HTTPS/SSH 链接，将我们的代码 push 即可

自定义远程库链接： Define remote，给远程库链接定义个 name，然后再 URL里面填入码云远程库的 HTTPS链接即可，码云服务器在国内，用 HTTPS 链接即可，没必要用 SSH 免密链接

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011544612.png)

## pull拉取远程库到本地库
我们在远程库修改代码，然后使用本地库 pull 拉取远程库的代码

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011544697.png)

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011544356.png)

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011544703.png)

## clone克隆远程库到本地库

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011545493.png)

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011545746.png)

## 码云复制Github项目
码云提供了直接复制 GitHub 项目的功能，方便我们做项目的迁移和下载 

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011545449.png)

将 GitHub的远程库 HTTPS链接复制过来，点击创建按钮即可。

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011545542.png)

如果GitHub项目更新了以后，在码云项目端可以手动重新同步，进行更新！

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011545871.png)



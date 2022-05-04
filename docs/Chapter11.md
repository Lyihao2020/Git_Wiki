# 第十一讲 ：使用Git进行团队协作

## 团队协作

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011218129.png)

举个例子：岳不群首先用 git 初始化自己的本地库，写了一套华山剑法，利用
push 命令将自己的本地库推送到代码托管中心(Github、Gitee)，大弟子令狐
冲通过 clone 克隆命令完整的复制到自己的本地库，令狐冲修改两招之后将
自己的本地库再次 push 到代码托管中心，这样岳不群就可以通过 pull 命令
拉取令狐冲修改的代码 来更新自己的本地库。

## 跨团队协作

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011218000.png)

令狐冲请东方不败改代码，东方不败通过 fork 命令从岳不群的的远程库中拿取代码，再通过 clone 克隆命令到自己的本地库，修改完成后使用 push 推送到在自己的远程库，使用 Pull request 拉取请求给岳不群，岳不群审核完成后使用 merge 命令合并对方的代码到自己的远程库中，再通过 pull 命令到自己的本地库中，这样修改过后的华山剑法岳不群和令狐冲就都可以使用了。

## GitHub

#### ①、Gihub

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011219106.png)

### 远程仓库操作

| 命令名称            | 作用                         |
| ------------------- | ---------------------------- |
| git remote -v   | 查看当前所有远程地址别名                    |
| git remote add 别名 远程地址    | 起别名                     |
| git push 别名 分支 | 推送本地分支上的内容克隆到本地                     |
| git clone 远程地址   | 将远程仓库的内容克隆到本地 |
| git pull 远程库地址别名 远程分支名  | 将远程仓库对于分支最新内容拉下来后与当前本地分支直接合并 |

### 创建远程仓库别名

基本语法：

- `git remote -v` 查看当前所有远程地址别名
- `git remote add 别名 远程地址` 起别名

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011223696.png)

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011223032.png)

**注意：起的别名最好和本地库的名称一致**

#### ②、Gitee

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011225997.png)

### 推送本地分支到远程仓库

基本语法：`git push 别名 分支`

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011503487.png)

我们输入 gitee 的用户名和密码，会提示推送成功，我们在 gitee 上查看我们的 git-demo 仓库，发现有我们推送的hello.txt 文件

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011503450.png)

### 拉取远程库分支到本地库

语法：`git pull 别名 分支`

我们在远程库进行 hello.txt 的文件修改

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011503465.png)

然后在本地库将远程库的代码 拉取

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011504408.png)

### 克隆远程仓库到本地

基本语法：`git clone 远程地址`

我们另一台用户需要克隆我们的远程仓库到他的本地库，由于是使用一台电脑模拟，所以在克隆之前需要在 凭据管理器下删除我们之前的 gitee 凭据

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011504741.png)

我们新建一个文件夹 git-clone，然后在此文件夹下右键 git bash here，之后进行克隆

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011505099.png)

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011505574.png)

## 邀请加入团队

### Gitee

我们在 git-clone(假设这是大弟子令狐冲) 文件夹里面进行代码修改，修改完后添加到暂存区，再提交到本地库，之后 push 到我们的远程库

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011506768.png)

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011507392.png)

我们在 git-demo 仓库点击管理 -> 仓库成员管理 -> 添加仓库成员 -> 邀请用户

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011508007.png)

我们在第二个gitee 账号里面可以接收到如下图：

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011508147.png)

令狐成成为仓库开发者被拉入团队后，我们再次在令狐冲文件夹使用进行 push

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011509474.png)

push 到远程库成功，我们在远程库查看

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011509271.png)

## GitHub

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011509932.png)

填入想要合作的人

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011510195.png)

复制地址并发给该用户

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011510893.png)

在 atguigulinghuchong这个账号 中的 地址 栏 复制 收到邀请 的 链接 ，点击接受邀请。

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011510783.png)

## 跨团队协作

### Gitee

将远程仓库的地址复制发给邀请跨团队协作的人，比如东方不败。

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011511496.png)

在东方不败的 Gitee账号里的地址栏复制收到的链接，然后点击 Fork将项目叉到自己的本地仓库

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011511525.png)

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011512933.png)

接下来点击上方的 Pull Requests 请求，并创建一个新的请求 。

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011512343.png)

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011512669.png)

合并之后我们在岳不群的 git-demo 下就可以看到东方不败的代码

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011512543.png)

### GitHub

将远程仓库的地址复制发给邀请跨团队协作的人，比如东方不败。

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011513507.png)

在东方不败的 GitHub账号里的地址栏复制收到的链接，然后点击 Fork将项目叉到自己的本地仓库

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011513004.png)

东方不败就可以在线编辑叉取过来的文件。编辑完毕后，填写描述信息并点击左下角绿色按钮提交。

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011513339.png)


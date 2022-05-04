# 第十二讲 ：SSH免密登陆



## Gitee

在 C盘 User 自己的账户下右键 git bash here，`ssh-keygen -t rsa -C 自己的邮箱签名`

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011517033.png)

这样就会生成 .ssh 文件夹，里面有私钥和公钥

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011517991.png)

之后在 gitee 上添加公钥

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011517000.png)

这样我们可以借助 ssh 链接来拉取和推送代码，并且不需要进行登录

## GitHub

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011518192.png)

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011518259.png)

![在这里插入图片描述](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011519779.png)


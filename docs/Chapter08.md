# 第八讲 ：码云注册使用



> **github 是有墙的，比较慢，在国内的话，我们一般使用 gitee ，公司中有时候会搭建自己的gitlab服务器**

这个其实可以作为大家未来找工作的一个重要信息！

1、注册登录码云，完善个人信息

![图片](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011130626.jpeg)

2、设置本机绑定SSH公钥，实现免密码登录！（免密码登录，这一步挺重要的，码云是远程仓库，我们是平时工作在本地仓库！)

```
# 进入 C:\Users\Administrator\.ssh 目录
# 生成公钥
ssh-keygen
```

![图片](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011131389.jpeg)

3、将公钥信息public key 添加到码云账户中即可！

![图片](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011131795.png)

4、使用码云创建一个自己的仓库！

![图片](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011132606.png)

许可证：开源是否可以随意转载，开源但是不能商业使用，不能转载，...  限制！

![图片](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011132153.jpeg)

克隆到本地！

![图片](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011132244.jpeg)

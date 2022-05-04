# 第六讲 : Git项目搭建[重要]



## 创建工作目录与常用指令

工作目录（WorkSpace)一般就是你希望Git帮助你管理的文件夹，可以是你项目的目录，也可以是一个空目录，<u>建议不要有中文</u>。

日常使用只要记住下图6个命令

![图片](https://gitee.com/liangjie0509/MarkdownPhoto/raw/main/img/202205011120921.png)

## 本地项目的搭建

创建本地仓库的方法有两种：一种是创建全新的仓库，另一种是克隆远程仓库。

1. 创建全新的仓库，需要用GIT管理的项目的根目录执行：

   ```git
   # 在当前目录新建一个Git代码库
   $ git init
   ```

2. 执行后可以看到，仅仅在项目目录多出了一个.git目录，关于版本等的所有信息都在这个目录里面。

## 克隆远程仓库

1. 另一种方式是克隆远程目录，由于是将远程服务器上的仓库完全镜像一份至本地！

   ```git
   
   # 克隆一个项目和它的整个代码历史(版本信息)
   $ git clone [url]  # https://gitee.com/kuangstudy/openclass.git
   ```

2. 去 gitee 或者 github 上克隆一个测试！

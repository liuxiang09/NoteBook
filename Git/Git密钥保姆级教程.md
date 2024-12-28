 

![在这里插入图片描述](https://img-blog.csdnimg.cn/b88c49c5b7e04dacaaed7cf2fc928687.gif#pic_center)

> *   **博主简介：22级计算机科学与技术本科生一枚🌸**
> *   **博主主页：[是瑶瑶子啦](https://blog.csdn.net/Yaoyao2024?spm=1011.2444.3001.5343)**
> *   **每日一言🌼:** “当人们做不到一些事情的时候，他们会对你说你也同样不能。”——《当幸福来敲门》  
>     克里斯加德纳

#### Git配置SSH Key

*   [一、什么是Git?](#Git_9)
*   [二、什么是SSL？什么是公钥和密钥？](#SSL_14)
*   [三、Git配置](#Git_37)

一、什么是Git?
---------

> Git是一个开源的分布式版本控制系统，可以有效、高速的处理从很小到非常大的项目版本管理1。Git 是 Linus Torvalds 为了帮助管理 Linux 内核开发而开发的一个开放源码的版本控制**软件**。

![在这里插入图片描述](https://img-blog.csdnimg.cn/a889b56362764e85be18fcd8d0d8bc07.png)

二、什么是SSL？什么是公钥和密钥？
------------------

> SSH (Secure Shell) 密钥是用于身份验证和加密通信的一对加密密钥。它由两个部分组成：**私钥（private key）和公钥（public key）**。这对密钥是通过非对称加密算法生成的，其中**私钥用于加密数据，而公钥用于解密数据**。

在 SSH 中，私钥应该保持在你的本地计算机上，并且必须保持安全和保密。公钥则可以被分享给其他人或服务器。当你连接到一个远程服务器时，你可以将你的公钥添加到服务器上，以便服务器可以使用该公钥对你的身份进行验证。

当你使用 SSH 协议连接到远程服务器时，身份验证过程如下：

1.  你的本地计算机向服务器发送请求。
    
2.  服务器要求提供身份验证凭据。
    
3.  你的本地计算机将使用你的私钥对一个随机生成的数字进行加密，并将加密后的数字发送给服务器。
    
4.  服务器使用你之前提供的公钥对加密后的数字进行解密。  
    如果解密后的数字与服务器生成的数字匹配，服务器将验证你的身份并允许你登录。
    

使用 SSH 密钥对身份验证具有以下优势：

**安全性：** SSH 密钥使用非对称加密算法，提供更高的安全性，比密码身份验证更难以被破解。

**方便性：**你不需要记住复杂的密码，只需要使用你的私钥来访问远程服务器。

**可信任性** 公钥可以在多个服务器之间共享，而不需要使用相同的密码。

通过生成 SSH 密钥对并将公钥添加到服务器上，你可以实现**更安全和方便的远程访问。**

三、Git配置
-------

首先打开`Git Bash`

*   **1.配置用户名和邮箱信息**

    git config --global user.name “username”
    git config --global user.email “email”
    

> 注意`“username”`和`“email”`和前面单词之间有一个空格！

*   **2.生成SSH Key**

    # 你的Github绑定的邮箱
    ssh-keygen -t rsa -C "***@gmail.com"
    

*   **3.获取SSH Key**

根据命令行提示，进入文件夹，获取以`ssh-rsa`的字符串（包括`ssh-rsa`)  
![在这里插入图片描述](https://img-blog.csdnimg.cn/53764004f1414ac89a8ceca6d7e4d1b1.png)  
![在这里插入图片描述](https://img-blog.csdnimg.cn/9229991d27d1433fb81c38f5867a1c42.png)

*   **4.在github添加SSH Key**

![在这里插入图片描述](https://img-blog.csdnimg.cn/21d323789c5f41248eee5de8d6fe36f2.png)  
![在这里插入图片描述](https://img-blog.csdnimg.cn/3d1d4bb965f340c9905dd5a581efbfb5.png)

> title：自定  
> SSH：复制刚才拷贝的

*   **5.检测是否配置成功**  
    本地`git-bash`输入以下命令

    $ ssh -T git@github.com
    

若显示如下，则代表配置成功！🎉🎉🎉  
![在这里插入图片描述](https://img-blog.csdnimg.cn/5ab3986c95f4474bb80aa1b996553bc9.png)

* * *

![在这里插入图片描述](https://img-blog.csdnimg.cn/dd52615e6d4d419bb71365add1e3c7ac.png#pic_center)

*   [Java岛冒险记【从小白到大佬之路】  
    ](https://blog.csdn.net/yaoyao2024/category_12168376.html)
    
*   [LeetCode每日一题–进击大厂](https://blog.csdn.net/yaoyao2024/category_12115665.html)
    
*   [Go语言核心编程  
    ](https://blog.csdn.net/yaoyao2024/category_12291040.html)
    
*   [算法](https://blog.csdn.net/yaoyao2024/category_12251293.html)
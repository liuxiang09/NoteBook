 

### 本文章作者本人卸载之后重新安装的完整详细教程, 包含了环境变量的详细配置,以及常见的错误解决方法

![](https://img-blog.csdnimg.cn/img_convert/074b13c46edb408b866f35221b5d017f.jpeg)

一. [node.js](https://so.csdn.net/so/search?q=node.js&spm=1001.2101.3001.7020)安装与环境变量配置
--------------------------------------------------------------------------------------

### 1 .node.js下载(包含国内和国外下载地址)

#### 1.国外的官网地址: [Node.js (nodejs.org)](https://nodejs.org/en "Node.js (nodejs.org)") 下载慢,下面提供国内地址.

可以看到当前的版本 [LTS](https://so.csdn.net/so/search?q=LTS&spm=1001.2101.3001.7020)是大多用户使用的稳定版本, Current是最新版本, 这里选择的是稳定版本(18.15.0)

![](https://img-blog.csdnimg.cn/img_convert/78b39ebe20ad4c6284f25c5b48866c7f.png)

点击如下图所示位置Downloads 进行node.js下载

![](https://img-blog.csdnimg.cn/img_convert/7b4b2b6d4c514cf19e2ed74d1e00d759.png)

#### 2.国内下载地址: [下载 | Node.js 中文网 (nodejs.cn)](https://nodejs.cn/download/current/ "下载 | Node.js 中文网 (nodejs.cn)")

点击最新版本,点击Windows安装包 进行下载安装, 如下

![](https://img-blog.csdnimg.cn/img_convert/eda80bab964948ca81ea637f5687bb37.png)

### 2\. node.js详细安装步骤

1.  #### 打开下载安装的文件夹下的安装包, 双击进行安装
    

![](https://img-blog.csdnimg.cn/img_convert/d7ec286029584d3996993943b909fcd2.png)

1.  #### 点击next 下一步
    

![](https://img-blog.csdnimg.cn/img_convert/453404fb773c4628a39670a27e35d298.png)

1.  #### 勾选点击下一步next
    

![](https://img-blog.csdnimg.cn/img_convert/09bc99a3f4e84d6cb131dc883831071d.png)

1.  #### 选择安装的位置最好是英文路径,我的是D\\NodeJs\\node\ ,然后点击下一步next
    

![](https://img-blog.csdnimg.cn/img_convert/ed6297770c584966a4be6146c9d8bcf2.png)

![](https://img-blog.csdnimg.cn/img_convert/82123ff4e48e4f888566570bc2df72ec.png)

1.  #### 点击下一步next
    

![](https://img-blog.csdnimg.cn/img_convert/4607e38b93d44a26ab3f9f7947d4b167.png)

1.  #### 看到如下图所示, 不要勾选!不要勾选! 不要勾选! 直接next
    

![](https://img-blog.csdnimg.cn/img_convert/156d43049a2a4ddcbce8e2ee3d05bc42.png)

如果勾选了就会出现了这样的界面下载完成之后会出现

![](https://img-blog.csdnimg.cn/img_convert/f41e7a93dda74a5fb3431f304b690b7d.png)

![](https://img-blog.csdnimg.cn/img_convert/9c1f45bfe36348ec91677d75ac55357f.png)

#### 7.点击安装install

![](https://img-blog.csdnimg.cn/img_convert/f698aeae74b14324906856c6711710ad.png)

![](https://img-blog.csdnimg.cn/img_convert/9d508898ff11450ea766085ee5b7512e.png)

#### 8.完成安装,点击Finish

![](https://img-blog.csdnimg.cn/img_convert/036639b01b2a456f93555f81aedb12eb.png)

### 3\. 详细配置环境变量

1.  #### 找到电脑的环境变量 , 我这是Windows11 系统
    

![](https://img-blog.csdnimg.cn/img_convert/9862a6fdcd8a4d8ca3c256f739878146.png)

#### 2.进入环境变量，编辑【系统变量】下的变量【Path】, 点击编辑

![](https://img-blog.csdnimg.cn/img_convert/150fee0277a14b2f88d25ffd16f872cc.png)

#### 3.添加安装路径 我的是D:\\NodeJs\\nodejs\

![](https://img-blog.csdnimg.cn/img_convert/c61fd435192b408e84fd6e0b9042af59.png)

二. 验证是否安装成功!
------------

### 1.进入[cmd命令](https://so.csdn.net/so/search?q=cmd%E5%91%BD%E4%BB%A4&spm=1001.2101.3001.7020 "cmd命令")行窗口，右键进行管理员模式下,输入命令, 查看nodejs版本

     node -v

![](https://img-blog.csdnimg.cn/img_convert/5a0bfabe928f4e098fd7f0cf783fa4af.png)

### 2\. 查看npm版本 如下图所示，即为安装成功：

     npm -v

![](https://img-blog.csdnimg.cn/img_convert/c50fd3c6182243458ce32ae2fa748dbb.png)

三. 修改下载位置
---------

### **1.查看npm默认存放位置**

查看npm全局模块的存放路径

     npm get prefix

查看npm缓存默认存放路径

     npm get cache

![](https://img-blog.csdnimg.cn/img_convert/836f71b7f3674026a26e9284a92d9418.png)

如上图所示，npm 全局模块存放位置以及cache的存放位置，默认是在 C 盘 “C:\\Users\\用户\\AppData” 下。

### **2.在 nodejs 安装目录下，创建 “node\_global” 和 “node\_cache” 两个文件夹**

![](https://img-blog.csdnimg.cn/img_convert/ae1bdecca3dc40af801db8f4d2e9fd18.png)

### **3.修改默认文件夹**

设置全局模块的安装路径到 “node_global” 文件夹 npm config set prefix 命令

     npm config set prefix  "D:\NodeJs\nodejs\node_global"

![](https://img-blog.csdnimg.cn/img_convert/48d8ba9528f44dc4963c5183636eb054.png)

设置缓存到 “node_cache” 文件夹 npm config set cache 命令

注意看路径不要写错了喔!!!

     npm config set cache "D:\NodeJs\nodejs\node_cache"

![](https://img-blog.csdnimg.cn/img_convert/c58a93fdc25f4af5864252086b332690.png)

在系统变量的环境变量中配置node_global 的路径,方便执行命令

![](https://img-blog.csdnimg.cn/img_convert/b9647448ee5d49e38b7ffe64d394ab78.png)

### 4\. 查看是否修改成功

使用命令

     npm install express -g

![](https://img-blog.csdnimg.cn/img_convert/f9ad70b0e9f34d9ca82a046a0246a258.png)

![](https://img-blog.csdnimg.cn/img_convert/5ea379971251498eadd75fd0d1364382.png)

如上图所示，下载express模块成功，然后在文件管理器中查看是否保存到上面自定义的路径下。

![](https://img-blog.csdnimg.cn/img_convert/69432291ab9c49ae870af29ccd315f2c.png)

到这里就已经修改成功了

四、设置淘宝镜像
--------

### 1.将npm默认的registry修改为淘宝registry, 查看当前的镜像

     npm config get registry

![](https://img-blog.csdnimg.cn/img_convert/12abadff3644422c943e241a07782821.png)

1.  ### 设置淘宝镜像
    

     npm config set  registry  https://registry.npmmirror.com/

     npm config set registry https://registry.npm.taobao.org/  //即将停止解析

![](https://img-blog.csdnimg.cn/img_convert/f24fdbc875864d308cdfdc22f63212ec.png)

### 3\. 执行npm config get registry查看当前的镜像

     npm config get registry

![](https://img-blog.csdnimg.cn/img_convert/48a0abb2bf364459811d9f4949e58a30.png)

如上图所示，npm默认的registry已修改为淘宝镜像

1.  ### 安装淘宝源cnpm
    

已更改至最新

     npm install -g cnpm --registry=https://registry.npmmirror.com 

![](https://img-blog.csdnimg.cn/img_convert/8312d72c92d94c0d8001be949ae3ae1d.png)

### 5\. 查看cnpm的模块是否安装成功在本地

![](https://img-blog.csdnimg.cn/img_convert/9a099cabb7904e30931e409043570bab.png)

#### 执行命令查看cnpm模块

     cnpm -v

![](https://img-blog.csdnimg.cn/img_convert/de500ecbd0c6474f98b642898fb9e8a9.png)

到这里就已经安装完毕.

如果遇到安装完cnpm时出现不是内部或外部命令，也不是可运行的程序。需要重新打开cmd才能正常安装。

五.卸载
----

如果需要卸载看另一篇博客:

文章地址: [2023年node.js完美卸载教程(保姆级别)_nodejs卸载-CSDN博客](https://blog.csdn.net/qq_60870118/article/details/129721973 "2023年node.js完美卸载教程(保姆级别)_nodejs卸载-CSDN博客")
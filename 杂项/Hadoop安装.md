## 环境

本实验使用 **CentOS 6.4 32位** 作为系统环境，请自行安装系统（可参考[使用VirtualBox安装CentOS](https://dblab.xmu.edu.cn/blog/164/)）。如果用的是 Ubuntu 系统，请查看相应的 [Ubuntu安装Hadoop教程](https://dblab.xmu.edu.cn/blog/install-hadoop/)。

本教程基于原生 Hadoop 2，在 **Hadoop 2.6.0 (stable)** 版本下验证通过，可适合任何 Hadoop 2.x.y 版本，例如 Hadoop 2.7.1, Hadoop 2.4.1等。



**Hadoop版本**: Hadoop 有两个主要版本，Hadoop 1.x.y 和 Hadoop 2.x.y 系列，比较老的教材上用的可能是 0.20 这样的版本。Hadoop 2.x 版本在不断更新，本教程均可适用。如果需安装 0.20，1.2.1这样的版本，本教程也可以作为参考，主要差别在于配置项，配置请参考官网教程或其他教程。

新版是兼容旧版的，书上旧版本的代码应该能够正常运行（我自己没验证，欢迎验证反馈）。



装好了 CentOS 系统之后，在安装 Hadoop 前还需要做一些必备工作。

## 创建hadoop用户

如果你安装 CentOS 的时候不是用的 "hadoop" 用户，那么需要增加一个名为 hadoop 的用户。

首先点击左上角的 “应用程序” -> "系统工具" -> "终端"，首先在终端中输入 `su` ，按回车，输入 root 密码以 root 用户登录，接着执行命令创建新用户 hadoop:

```bash
su              # 上述提到的以 root 用户登录useradd -m hadoop -s /bin/bash   # 创建新用户hadoop
```

Shell 命令

如下图所示，这条命令创建了可以登陆的 hadoop 用户，并使用 /bin/bash 作为shell。

![CentOS创建hadoop用户](https://dblab.xmu.edu.cn/blog/wp-content/uploads/2015/10/install-hadoop-centos-01-craete-user.png)

接着使用如下命令修改密码，按提示输入两次密码，可简单的设为 "hadoop"（密码随意指定，若提示“无效的密码，过于简单”则再次输入确认就行）:

```bash
passwd hadoop
```

Shell 命令

可为 hadoop 用户增加管理员权限，方便部署，避免一些对新手来说比较棘手的权限问题，执行：

```bash
visudo
```

Shell 命令

如下图，找到 `root ALL=(ALL) ALL` 这行（应该在第98行，可以先按一下键盘上的 `ESC` 键，然后输入 `:98` (按一下冒号，接着输入98，再按回车键)，可以直接跳到第98行 ），然后在这行下面增加一行内容：`hadoop ALL=(ALL) ALL` （当中的间隔为tab），如下图所示：

![为hadoop增加sudo权限](https://dblab.xmu.edu.cn/blog/wp-content/uploads/2015/10/install-hadoop-centos-02-add-sudo.png)

添加上一行内容后，先按一下键盘上的 `ESC` 键，然后输入 `:wq` (输入冒号还有wq，这是vi/vim编辑器的保存方法)，再按回车键保存退出就可以了。

最后注销当前用户(点击屏幕右上角的用户名，选择退出->注销)，在登陆界面使用刚创建的 hadoop 用户进行登陆。（如果已经是 hadoop 用户，且在终端中使用 `su` 登录了 root 用户，那么需要执行 `exit` 退出 root 用户状态）

## 准备工作

使用 hadoop 用户登录后，还需要安装几个软件才能安装 Hadoop。

CentOS 使用 yum 来安装软件，需要联网环境，首先应检查一下是否连上了网络。如下图所示，桌面右上角的网络图标若显示红叉，则表明还未联网，应点击选择可用网络。

![检查是否联网](https://dblab.xmu.edu.cn/blog/wp-content/uploads/2015/10/install-hadoop-centos-04-connect-to-net.png)

连接网络后，需要安装 SSH 和 Java。

## 安装SSH、配置SSH无密码登陆

集群、单节点模式都需要用到 SSH 登陆（类似于远程登陆，你可以登录某台 Linux 主机，并且在上面运行命令），一般情况下，CentOS 默认已安装了 SSH client、SSH server，打开终端执行如下命令进行检验：

```bash
rpm -qa | grep ssh
```

Shell 命令

如果返回的结果如下图所示，包含了 SSH client 跟 SSH server，则不需要再安装。

![检查是否安装了SSH](https://dblab.xmu.edu.cn/blog/wp-content/uploads/2015/10/install-hadoop-centos-03-install-ssh.png)

若需要安装，则可以通过 yum 进行安装（安装过程中会让你输入 [y/N]，输入 y 即可）：

```bash
sudo yum install openssh-clientssudo yum install openssh-server
```

Shell 命令

接着执行如下命令测试一下 SSH 是否可用：

```bash
ssh localhost
```

Shell 命令

此时会有如下提示(SSH首次登陆提示)，输入 yes 。然后按提示输入密码 hadoop，这样就登陆到本机了。

![测试SSH是否可用](https://dblab.xmu.edu.cn/blog/wp-content/uploads/2015/10/install-hadoop-centos-05-ssh-localhost.png)

但这样登陆是需要每次输入密码的，我们需要配置成SSH无密码登陆比较方便。

首先输入 `exit` 退出刚才的 ssh，就回到了我们原先的终端窗口，然后利用 ssh-keygen 生成密钥，并将密钥加入到授权中：

```bash
exit                           # 退出刚才的 ssh localhostcd ~/.ssh/                     # 若没有该目录，请先执行一次ssh localhostssh-keygen -t rsa              # 会有提示，都按回车就可以cat id_rsa.pub >> authorized_keys  # 加入授权chmod 600 ./authorized_keys    # 修改文件权限
```

Shell 命令



**~的含义**: 在 Linux 系统中，~ 代表的是用户的主文件夹，即 "/home/用户名" 这个目录，如你的用户名为 hadoop，则 ~ 就代表 "/home/hadoop/"。 此外，命令中的 # 后面的文字是注释。

此时再用 `ssh localhost` 命令，无需输入密码就可以直接登陆了，如下图所示。

![SSH无密码登录](https://dblab.xmu.edu.cn/blog/wp-content/uploads/2015/10/install-hadoop-centos-08-ssh-no-password.png)

## 安装Java环境

Java 环境可选择 Oracle 的 JDK，或是 OpenJDK，现在一般 Linux 系统默认安装的基本是 OpenJDK，如 CentOS 6.4 就默认安装了 OpenJDK 1.7。按 http://wiki.apache.org/hadoop/HadoopJavaVersions 中说的，Hadoop 在 OpenJDK 1.7 下运行是没问题的。需要注意的是，CentOS 6.4 中默认安装的只是 Java JRE，而不是 JDK，为了开发方便，我们还是需要通过 yum 进行安装 JDK，安装过程中会让输入 [y/N]，输入 y 即可：

```bash
sudo yum install java-1.7.0-openjdk java-1.7.0-openjdk-devel
```

Shell 命令



**JRE和JDK的区别**: JRE（Java Runtime Environment，Java运行环境），是运行 Java 所需的环境。JDK（Java Development Kit，Java软件开发工具包）即包括 JRE，还包括开发 Java 程序所需的工具和类库。

通过上述命令安装 OpenJDK，默认安装位置为 /usr/lib/jvm/java-1.7.0-openjdk（该路径可以通过执行 `rpm -ql java-1.7.0-openjdk-devel | grep '/bin/javac'` 命令确定，执行后会输出一个路径，除去路径末尾的 “/bin/javac”，剩下的就是正确的路径了）。OpenJDK 安装后就可以直接使用 java、javac 等命令了。

接着需要配置一下 JAVA_HOME 环境变量，为方便，我们在 ~/.bashrc 中进行设置（扩展阅读: [设置Linux环境变量的方法和区别](http://www.powerxing.com/linux-environment-variable/)）：

```bash
vim ~/.bashrc
```

Shell 命令

在文件最后面添加如下单独一行（指向 JDK 的安装位置），并保存：

```shell
export JAVA_HOME=/usr/lib/jvm/java-1.7.0-openjdk
```

Shell

如下图所示：

![设置JAVA_HOME环境变量](https://dblab.xmu.edu.cn/blog/wp-content/uploads/2015/10/install-hadoop-centos-10-set-java-home.png)

接着还需要让该环境变量生效，执行如下代码：

```bash
source ~/.bashrc    # 使变量设置生效
```

Shell 命令

设置好后我们来检验一下是否设置正确：

```bash
echo $JAVA_HOME     # 检验变量值java -version$JAVA_HOME/bin/java -version  # 与直接执行 java -version 一样
```

Shell 命令

如果设置正确的话，`$JAVA_HOME/bin/java -version` 会输出 java 的版本信息，且和 `java -version` 的输出结果一样，如下图所示：

![成功设置JAVA_HOME环境变量](https://dblab.xmu.edu.cn/blog/wp-content/uploads/2015/10/install-hadoop-centos-11-echo-java-home.png)

这样，Hadoop 所需的 Java 运行环境就安装好了。

## 安装 Hadoop 2

Hadoop 2 可以通过 http://mirror.bit.edu.cn/apache/hadoop/common/ 或者 http://mirrors.cnnic.cn/apache/hadoop/common/ 下载，本教程选择的是 2.6.0 版本，下载时请下载 **hadoop-2.x.y.tar.gz** 这个格式的文件，这是编译好的，另一个包含 src 的则是 Hadoop 源代码，需要进行编译才可使用。

下载时强烈建议也下载 **hadoop-2.x.y.tar.gz.mds** 这个文件，该文件包含了检验值可用于检查 hadoop-2.x.y.tar.gz 的完整性，否则若文件发生了损坏或下载不完整，Hadoop 将无法正常运行。

本文涉及的文件均通过浏览器下载，默认保存在 “下载” 目录中（若不是请自行更改 tar 命令的相应目录）。另外，如果你用的不是 2.6.0 版本，则将所有命令中出现的 2.6.0 更改为你所使用的版本。

```bash
cat ~/下载/hadoop-2.6.0.tar.gz.mds | grep 'MD5' # 列出md5检验值# head -n 6 ~/下载/hadoop-2.7.1.tar.gz.mds # 2.7.1版本格式变了，可以用这种方式输出md5sum ~/下载/hadoop-2.6.0.tar.gz | tr "a-z" "A-Z" # 计算md5值，并转化为大写，方便比较
```

Shell 命令

若文件不完整则这两个值一般差别很大，可以简单对比下前几个字符跟后几个字符是否相等即可，如下图所示，如果两个值不一样，请务必重新下载。

![检验文件完整性](https://dblab.xmu.edu.cn/blog/wp-content/uploads/2015/10/install-hadoop-centos-12-md5.png)

我们选择将 Hadoop 安装至 /usr/local/ 中：

```bash
sudo tar -zxf ~/下载/hadoop-2.6.0.tar.gz -C /usr/local    # 解压到/usr/local中cd /usr/local/sudo mv ./hadoop-2.6.0/ ./hadoop            # 将文件夹名改为hadoopsudo chown -R hadoop:hadoop ./hadoop        # 修改文件权限
```

Shell 命令

Hadoop 解压后即可使用。输入如下命令来检查 Hadoop 是否可用，成功则会显示 Hadoop 版本信息：

```bash
cd /usr/local/hadoop./bin/hadoop version
```

Shell 命令



**相对路径与绝对路径**: 请务必注意命令中的相对路径与绝对路径，本文后续出现的 `./bin/...`，`./etc/...` 等包含 ./ 的路径，均为相对路径，以 /usr/local/hadoop 为当前目录。例如在 /usr/local/hadoop 目录中执行 `./bin/hadoop version` 等同于执行 `/usr/local/hadoop/bin/hadoop version`。可以将相对路径改成绝对路径来执行，但如果你是在主文件夹 ~ 中执行 `./bin/hadoop version`，执行的会是 `/home/hadoop/bin/hadoop version`，就不是我们所想要的了。

## Hadoop单机配置(非分布式)

Hadoop 默认模式为非分布式模式，无需进行其他配置即可运行。非分布式即单 Java 进程，方便进行调试。

现在我们可以执行例子来感受下 Hadoop 的运行。Hadoop 附带了丰富的例子（运行 `./bin/hadoop jar ./share/hadoop/mapreduce/hadoop-mapreduce-examples-2.6.0.jar` 可以看到所有例子），包括 wordcount、terasort、join、grep 等。

在此我们选择运行 grep 例子，我们将 input 文件夹中的所有文件作为输入，筛选当中符合正则表达式 `dfs[a-z.]+` 的单词并统计出现的次数，最后输出结果到 output 文件夹中。

```bash
cd /usr/local/hadoopmkdir ./inputcp ./etc/hadoop/*.xml ./input   # 将配置文件作为输入文件./bin/hadoop jar ./share/hadoop/mapreduce/hadoop-mapreduce-examples-*.jar grep ./input ./output 'dfs[a-z.]+'cat ./output/*          # 查看运行结果
```

Shell 命令

若运行出错，如出现如下图提示：

![运行Hadoop实例时可能会报错](https://dblab.xmu.edu.cn/blog/wp-content/uploads/2015/10/install-hadoop-centos-13-hostname.png)

若出现提示 "WARN util.NativeCodeLoader: Unable to load native-hadoop library for your platform... using builtin-java classes where applicable"，该 WARN 提示可以忽略，不会影响 Hadoop 正常运行（可通过编译 Hadoop 源码解决，解决方法请自行搜索）。

若出现提示 "INFO metrics.MetricsUtil: Unable to obtain hostName java.net.UnknowHostException"，这需要执行如下命令修改 hosts 文件，为你的主机名增加IP映射：

```bash
sudo vim /etc/hosts
```

Shell 命令

主机名在终端窗口标题里可以看到，或执行命令 `hostname` 查看，如下图所示，在最后面增加一行 "127.0.0.1 dblab"：

![设置主机名的IP映射](https://dblab.xmu.edu.cn/blog/wp-content/uploads/2015/10/install-hadoop-centos-14-set-hostname.png)

保存文件后，重新运行 hadoop 实例，若执行成功的话会输出很多作业的相关信息，最后的输出信息如下图所示。作业的结果会输出在指定的 output 文件夹中，通过命令 `cat ./output/*` 查看结果，符合正则的单词 dfsadmin 出现了1次：

![Hadoop例子输出结果](https://dblab.xmu.edu.cn/blog/wp-content/uploads/2015/10/install-hadoop-centos-15-example-output.png)

**注意**，Hadoop 默认不会覆盖结果文件，因此再次运行上面实例会提示出错，需要先将 `./output` 删除。
## 一、（虚拟机）共享文件夹无法找到

```bash
sudo vmhgfs-fuse .host:/ /mnt/hgfs -o allow_other
```

然后到/mnt/hgfs/ubuntu共享文件夹下可以找到从win共享文件

## 二、查看电脑存储

在 Ubuntu 中，您可以使用图形界面或命令行查看电脑的存储使用情况。以下是几种常用的方法：

------

### **1. 使用图形界面查看存储**

1. **文件管理器**：
   - 打开文件管理器（一般叫“文件”或“Files”）。
   - 左侧栏会显示硬盘分区及其可用空间。
2. **磁盘工具**：
   - 打开“应用程序菜单”。
   - 搜索并启动 **Disks** 或 **磁盘工具**。
   - 在界面中可以看到所有硬盘分区及其容量和使用情况。

------

### **2. 使用命令行查看存储**

#### **方法 1：使用 `df` 命令**

运行以下命令查看存储使用情况：

```
df -h
```

- **Size**：分区的总大小。
- **Used**：已用空间。
- **Avail**：可用空间。
- **Use%**：使用百分比。
- **Mounted on**：挂载点（即分区对应的路径）。

#### **方法 2：使用 `lsblk` 命令**

查看硬盘分区及其挂载情况：

```
lsblk
```

- **NAME**：设备名称。
- **SIZE**：分区大小。
- **MOUNTPOINT**：挂载点。

#### **方法 3：使用 `du` 命令**

如果您想查看特定目录的存储使用情况：

```
du -sh /path/to/directory
```

#### **方法 4：使用 `fdisk` 命令**

查看硬盘分区详细信息：

```
sudo fdisk -l
```

------

## 三、ubuntu文件操作

### **1. 创建文件**

#### **创建空文件**

使用 `touch` 命令：

```
touch filename
```

#### **创建文件并写入内容**

使用 `echo` 命令：

```
echo "内容" > filename
```

使用 `cat` 命令：

```
cat > filename
```

输入内容后按 `Ctrl+D`保存。

#### **创建文件夹**

使用 `mkdir` 命令：

```
mkdir foldername
```

------

### **2. 删除文件**

#### **删除单个文件**

使用 `rm` 命令：

```
rm filename
```

#### **删除文件夹**

删除空文件夹：

```
rmdir foldername
```

删除非空文件夹及其内容：

```
rm -r foldername
```

#### **强制删除**

使用 `-f` 参数强制删除文件或文件夹：

```
rm -rf foldername
```

------

### **3. 移动文件**

#### **移动文件或重命名**

使用 `mv` 命令：

```sh
mv source destination	# 移动文件
mv oldname.txt newname.txt # 重命名文件
```

------

### **4. 查找文件**

#### **按名称查找**

使用 `find` 命令：

```
find /path/to/search -name "filename"
```

#### **按类型查找**

查找目录：

```
find /path/to/search -type d -name "foldername"
```

#### **按内容查找**

使用 `grep` 命令：

```
grep "内容" filename
```

#### **全局查找**

使用 `locate` 命令（需要安装 `mlocate`）：

```
locate filename
```

------

### **5. 复制文件**

#### **复制单个文件**

使用 `cp` 命令：

```
cp source destination
```

#### **复制文件夹**

使用 `-r` 参数递归复制文件夹：

```
cp -r source_folder destination
```

------

### **6. 其他文件操作技巧**

- 赋予执行权限：

  ```
  chmod +x filename
  ```

## 四、deb包安装方法

在Ubuntu系统中，安装`.deb`包的命令是`dpkg`。以下是具体的操作方法：

### 0. 用`dpkg`命令安装

```bash
sudo dpkg -i [deb文件路径]
```

- `-i`参数表示安装。
- 如果`[deb文件路径]`是文件名，确保当前目录下有该文件；如果是路径，请确保路径正确。

在 Ubuntu 中，`.deb` 文件是 Debian 软件包格式，安装后其内容会被解压到系统的特定目录。如果你想手动查看或提取 `.deb` 文件的内容，可以使用以下方法：

---

### **1. 查看 `.deb` 文件内容**
使用 `dpkg -c` 命令列出 `.deb` 文件包含的所有文件：
```bash
dpkg -c /path/to/package.deb
```
---

### **2. 提取 `.deb` 文件内容（不解压安装）**
#### **方法 1：使用 `dpkg -x`（提取文件到当前目录）**
```bash
dpkg -x /path/to/package.deb .
```
这会将 `.deb` 文件的内容解压到当前目录下的子文件夹中。

#### **方法 2：使用 `ar` 和 `tar`（手动解压）**
`.deb` 文件实际上是 `ar` 归档文件，包含 `control.tar.gz`（控制脚本）和 `data.tar.xz`（实际文件）：
```bash
# 解包 .deb 文件
ar x package.deb
```
解压后，你会得到：
- `control.tar.gz`（包含安装脚本、依赖信息等）
- `data.tar.xz`（包含实际要安装的文件）
- `debian-binary`（版本信息）

然后解压 `data.tar.xz`：
```bash
tar -xf data.tar.xz
```
解压后，文件会出现在当前目录的 `usr/`、`bin/`、`lib/` 等子目录中。

---

### **3. `.deb` 安装后文件的默认存放位置**
`.deb` 安装后，文件会按照 Linux 文件系统标准（FHS）分布到以下目录：
- **二进制可执行文件** → `/usr/bin/` 或 `/bin/`
- **库文件** → `/usr/lib/` 或 `/lib/`
- **配置文件** → `/etc/`
- **文档** → `/usr/share/doc/`
- **头文件** → `/usr/include/`
- **桌面应用** → `/usr/share/applications/`

#### **查找已安装 `.deb` 包的文件**
```bash
# 列出某个包安装的所有文件
dpkg -L package-name
```
示例（查找 `curl` 安装的文件）：
```bash
dpkg -L curl
```

#### **反向查找某个文件属于哪个包**
```bash
dpkg -S /path/to/file
```
示例：
```bash
dpkg -S /usr/bin/curl
```

---

### **4. 手动安装 `.deb` 文件**
如果只是想安装 `.deb` 文件（而不是提取内容），可以使用：
```bash
sudo apt install ./package.deb  # Ubuntu 16.04+
```
或
```bash
sudo dpkg -i package.deb
sudo apt-get install -f  # 修复依赖问题（如果有）
```

---

### **总结**
| 需求               | 命令                             |
| ------------------ | -------------------------------- |
| 查看 `.deb` 内容   | `dpkg -c package.deb`            |
| 提取 `.deb` 文件   | `dpkg -x package.deb .`          |
| 列出已安装包的文件 | `dpkg -L package-name`           |
| 查找文件所属包     | `dpkg -S /path/to/file`          |
| 安装 `.deb`        | `sudo apt install ./package.deb` |

如果你只是想检查 `.deb` 文件的内容，推荐使用 `dpkg -c`；如果需要手动提取文件，用 `dpkg -x` 或 `ar` + `tar` 解压。



## 五、imwheel启动以后，鼠标侧键和中键工作异常

我在 Ubuntu 上遇到了类似的问题，并找到了一种可能对其他人有帮助的解决方法。安装`imwheel`修复鼠标滚动问题后，我注意到滚动缩放和前进/后退鼠标按钮无法按预期工作。

基于以下解决方案[@soji256](https://github.com/soji256)和[@emmanuelvlad](https://github.com/emmanuelvlad)，我添加了几行代码来处理鼠标上的前进和后退按钮。具体操作如下：

1. 打开一个终端。
2. 键入以在文本编辑器中`nano ~/.imwheelrc`打开文件。`.imwheelrc`
3. 将文件内容替换为以下配置(`xprop | grep WM_CLASS`这个命令可以点击查看当前软件的ID)：

```
"(firefox_firefox)|(google-chrome)|(discord)|(brave)|(code)|(spotify)|(notion.*)|(mailspring)|(slack)|(inkscape)"
None,      Thumb1,   Alt_L|Left
None,      Thumb2,   Alt_L|Right
Control_L, Up,       Control_L|Button4
Control_L, Down,     Control_L|Button5
Control_R, Up,       Control_R|Button4
Control_R, Down,     Control_R|Button5
Shift_L,   Up,       Shift_L|Button4
Shift_L,   Down,     Shift_L|Button5
```

1. 按`Ctrl+X`关闭编辑器，然后按`Y`保存更改。
2. `imwheel`使用命令重新启动`killall imwheel && imwheel`。

此配置将`Thumb1`（`Thumb2`通常是鼠标上的前进和后退按钮）映射到大多数浏览器和文件管理器中的后退和前进操作。

为了确保`imwheel`在启动时启动，您可以将其添加`imwheel`到`.bashrc`文件中。操作方法如下：

1. 在终端中，输入`echo "imwheel" >> ~/.bashrc`或`echo "imwheel" >> ~/.zshrc`如果您正在使用`zsh`。

我希望这能帮助遇到同样问题的人！

参考：

- [编辑配置文件](https://wiki.archlinux.org/title/IMWheel#Edit_your_configuration_file)
- [如何解决按 Alt+Tab 后出现滚动异常行为？](https://askubuntu.com/a/1143466)
- [如何在登录时自动启动应用程序？](https://askubuntu.com/a/48327)
- [设置`wheel`开机自启动](https://blog.csdn.net/qq_32767041/article/details/84034280?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522216d2e79b01ba6ced5accd70eee2089a%2522%252C%2522scm%2522%253A%252220140713.130102334.pc%255Fall.%2522%257D&request_id=216d2e79b01ba6ced5accd70eee2089a&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~first_rank_ecpm_v1~rank_v31_ecpm-1-84034280-null-null.142^v102^pc_search_result_base9&utm_term=imwheel%E5%BC%80%E6%9C%BA%E8%87%AA%E5%90%AF%E5%8A%A8&spm=1018.2226.3001.4187)

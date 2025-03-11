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

- 输出示例：

  ```
  Filesystem      Size  Used Avail Use% Mounted on
  /dev/sda1        50G   20G   30G  40% /
  tmpfs           7.8G     0  7.8G   0% /dev/shm
  /dev/sdb1       100G   60G   40G  60% /mnt/data
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

- 输出示例：

  ```
  plaintext复制代码NAME   MAJ:MIN RM   SIZE RO TYPE MOUNTPOINT
  sda      8:0    0   500G  0 disk 
  ├─sda1   8:1    0    50G  0 part /
  └─sda2   8:2    0   450G  0 part /mnt/data
  sdb      8:16   0   100G  0 disk 
  └─sdb1   8:17   0   100G  0 part /mnt/backup
  ```

  - **NAME**：设备名称。
  - **SIZE**：分区大小。
  - **MOUNTPOINT**：挂载点。

#### **方法 3：使用 `du` 命令**

如果您想查看特定目录的存储使用情况：

```
du -sh /path/to/directory
```

- 输出示例：

  ```
  1.5G    /home/user/Documents
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

- 示例：

  ```
  touch myfile.txt
  ```

  创建一个名为 

  ```
  myfile.txt
  ```

   的空文件。

#### **创建文件并写入内容**

使用 `echo` 命令：

```
echo "内容" > filename
```

- 示例：

  ```
  echo "Hello, Ubuntu!" > hello.txt
  ```

使用 `cat` 命令：

```
cat > filename
```

- 示例：

  ```
  cat > notes.txt
  ```

  输入内容后按 

  ```
  Ctrl+D
  ```

   保存。

#### **创建文件夹**

使用 `mkdir` 命令：

```
mkdir foldername
```

- 示例：

  ```
  mkdir myfolder
  ```

------

### **2. 删除文件**

#### **删除单个文件**

使用 `rm` 命令：

```
rm filename
```

- 示例：

  ```
  rm myfile.txt
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

- 示例：

  ```
  rm -r myfolder
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

```
mv source destination
```

- 示例 1：移动文件到目标目录：

  ```
  mv myfile.txt /home/user/Documents
  ```

- 示例 2：重命名文件：

  ```
  mv oldname.txt newname.txt
  ```

#### **移动文件夹**

```
mv source_folder destination
```

- 示例：

  ```
  mv myfolder /home/user/Documents
  ```

------

### **4. 查找文件**

#### **按名称查找**

使用 `find` 命令：

```
find /path/to/search -name "filename"
```

- 示例：

  ```
  find /home -name "myfile.txt"
  ```

#### **按类型查找**

查找目录：

```
find /path/to/search -type d -name "foldername"
```

查找文件：

```
find /path/to/search -type f -name "filename"
```

#### **按内容查找**

使用 `grep` 命令：

```
grep "内容" filename
```

- 示例：

  ```
  grep "Ubuntu" myfile.txt
  ```

#### **全局查找**

使用 `locate` 命令（需要安装 `mlocate`）：

```
locate filename
```

- 示例：

  ```
  locate myfile.txt
  ```

------

### **5. 复制文件**

#### **复制单个文件**

使用 `cp` 命令：

```
cp source destination
```

- 示例：

  ```
  cp myfile.txt /home/user/Documents
  ```

#### **复制文件夹**

使用 `-r` 参数递归复制文件夹：

```
cp -r source_folder destination
```

- 示例：

  ```
  cp -r myfolder /home/user/Documents
  ```

------

### **6. 其他文件操作技巧**

#### **查看文件内容**

- 显示文件内容：

  ```
  cat filename
  ```

- 按页查看：

  ```
  less filename
  ```

- 查看前 N 行：

  ```
  head -n 10 filename
  ```

- 查看后 N 行：

  ```
  tail -n 10 filename
  ```

#### **修改文件权限**

- 修改读写权限：

  ```
  chmod 644 filename
  ```

- 赋予执行权限：

  ```
  chmod +x filename
  ```

------

### **总结**

- **创建**：`touch`、`mkdir`
- **删除**：`rm`、`rmdir`
- **移动**：`mv`
- **查找**：`find`、`grep`、`locate`
- **复制**：`cp`、`cp -r`

## 四、deb包安装方法

在Ubuntu系统中，安装`.deb`包的命令是`dpkg`。以下是具体的操作方法：

### 使用`dpkg`命令安装

bash复制

```bash
sudo dpkg -i [deb文件路径]
```

- `-i`参数表示安装。
- 如果`[deb文件路径]`是文件名，确保当前目录下有该文件；如果是路径，请确保路径正确。

#### 示例

假设你有一个名为`example.deb`的文件在当前目录下，可以运行以下命令：

bash复制

```bash
sudo dpkg -i example.deb
```

### 使用`apt`命令安装

`dpkg`命令安装时可能会出现依赖问题，而`apt`可以自动解决依赖关系。如果使用`dpkg`安装后出现依赖错误，可以运行以下命令来修复：

bash复制

```bash
sudo apt-get install -f
```

- `-f`参数表示修复损坏的包。

### 使用`gdebi`命令安装（推荐）

`gdebi`是一个更友好的工具，它会自动解决依赖问题。首先需要安装`gdebi`：

bash复制

```bash
sudo apt-get install gdebi
```

然后使用以下命令安装`.deb`包：

bash复制

```bash
sudo gdebi [deb文件路径]
```

#### 示例

bash复制

```bash
sudo gdebi example.deb
```

### 注意事项

- 确保你下载的`.deb`包来源可靠，避免安装恶意软件。
- 如果安装过程中提示权限不足，请确保使用`sudo`命令获取管理员权限。

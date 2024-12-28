# Linux ubuntu系统调试记录

## 共享文件夹无法找到

```bash
sudo vmhgfs-fuse .host:/ /mnt/hgfs -o allow_other
```

然后到/mnt/hgfs/ubuntu共享文件夹下可以找到从win共享文件
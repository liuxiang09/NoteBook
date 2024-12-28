# [从原理到实战，一份详实的 Scrapy 爬虫教程][https://cloud.tencent.com/developer/article/1856557]



## 使用

### 创建一个scrapy项目

```javascript
scrapy startproject mySpider
```

### 生成一个爬虫

```javascript
scrapy genspider demo "demo.cn"
```

### 提取数据

```js
完善spider 使用xpath等
```

```javascript
完善spider 使用xpath等
```

### 保存数据

```javascript
pipeline中保存数据
```

### 程序运行

在命令中运行爬虫

```javascript
scrapy crawl qb     # qb爬虫的名字
```

### 在pycharm中运行爬虫

```javascript
    from scrapy import cmdline
    cmdline.execute("scrapy crawl qb".split())
```


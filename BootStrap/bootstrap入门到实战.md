 

#### 目录

*   [1_认识Bootstrap](#1_Bootstrap_2)
*   *   [1.1_概念](#11__4)
    *   [1.2_起源和历史](#12__21)
    *   [1.3_Bootstrap优缺点](#13_Bootstrap_43)
*   [2_Bootstrap4的安装](#2_Bootstrap4_62)
*   *   [2.1_方式一 CDN](#21__09CDN_75)
    *   [2.2_方式二 : 下载源码引入](#22____132)
    *   [2.3_方式三 : npm安装](#23___npm_171)
*   [3_Bootstrap初体验](#3_Bootstrap_180)
*   [4_响应式容器原理](#4__246)
*   *   [4.1_屏幕尺寸的分割点（Breakpoints）](#41_Breakpoints_248)
    *   [4.2_响应式容器Containers](#42_Containers_260)
*   [5_网格系统（Grid system）](#5_Grid_system_276)
*   *   [5.1_认识](#51__278)
    *   [5.2_12列网格系统](#52_12_331)
    *   [5.3_网格系统的原理](#53__350)
    *   [5.4_嵌套(nesting)](#54_nesting_378)
    *   [5.5_自动布局（Auto-layout ）](#55_Autolayout__441)
    *   [5.7_响应式类（Responsive Class）](#57_Responsive_Class_536)
*   [6_响应式工具类](#6__571)
*   *   [6.1_认识](#61__573)
    *   [6.2_响应式工具类-Display](#62_Display_590)
    *   [6.3_实用的工具类（Utility classes）](#63_Utility_classes_621)
    *   [6.4_可访问性-辅助类（了解）](#64__639)
*   [7_Bootstrap组件](#7_Bootstrap_652)
*   [8_项目](#8__660)
*   *   [8.1_导航栏](#81__676)
    *   [8.2_轮播图](#82__727)
    *   [8.3_目标客户 版块](#83___885)

1_认识Bootstrap
-------------

### 1.1_概念

Bootstrap 读音 /ˈbu:tstræp/ ，是一个**非常受欢迎的前端框架**，官方网站将其描述为。

*   最流行的 HTML、CSS 和 JS 框架，用于在 Web 上开发响应式、移动优先的项目。(v3.x)
    *   响应式页面：页面布局会随着屏幕尺寸的变化而自动调整布局，作用是适配各个屏幕。
*   Bootstrap是功能强大、可扩展，且功能丰富的前端工具包。（v5.x）
*   Bootstrap底层是使用Sass构建，支持定制（Sass、Color、CSS variable …）。（v5.x）
*   Bootstrap中的网格系统、组件以及强大的JavaScript 插件可以快速搭建响应式网站。(v5.x)

简单的理解

*   Bootstrap是由HTML、CSS和JavaScript编写可复用代码的集合（包括全局样式、组件、插件等），它是一个前端框架，使用该框架能够快速开发出响应的网站（即适配PC、平板和移动端的网站）。
*   Bootstrap可以免去编写大量的 CSS 代码（Write less），让更专注于网站业务逻辑的开发。
*   Bootstrap是开源免费的，可以从GitHub直接拿到源码

  

### 1.2_起源和历史

Bootstrap原名Twitter Blueprint，由Twitter公司的Mark Otto和Jacob Thornton编写。

他们的本意是想制作一套可以让网页保持统一风格的前端框架。

在Bootstrap之前，Twitter团队在开发界面时，不同的项目组会使用不同的代码库。这样就会很容易导致界面风格不一致等问题，从而增加了后期的维护成本。

Mark Otto发现自己设计的工具比别人设计的更强大，能够做更多的事情。几个月之后，Mark Otto和一群开发人员做出了Bootstrap的原型。然后经过他们开发小组几个月之后的努力，大家把Twitter Blueprint改名为Bootstrap。

在2011年8月19日将其作为开源项目发布。项目由Mark Otto、Jacob Thornton和核心开发小组维护。

在2012年1月31日发布Bootstrap 2，增加了十二列网格系统和响应式组件，并对许多组件进行了修改。

在2013年8月19日发布Bootstrap 3，开始将移动设备优先作为方针，并且开始使用扁平化设计，支持IE8-9。

在2018年1月7日发布Bootstrap 4，增加了Flexbox Grid、Cards、Spacing Utilities等。

在2021年5月5日发布Bootstrap 5，增强Grid System、增强Form elements、Not Support for IE、Bootstrap Icons等

  

### 1.3_Bootstrap优缺点

**优点**

*   Bootstrap在Web开发人员中如此受欢迎的原因之一是它具有简单的文件结构，只需要懂HTML、CSS 和 JS 的基本知识，就可以上手使用Bootstrap，甚至阅读其源码，对于初学者来是说易于学习。
*   Bootstrap拥有一个强大的网格系统，它是由行和列组成，可以直接创建网格，无需自行编写媒体查询来创建。
*   Bootstrap预定义很多响应式的类。例如，给图片添加.img-responsive类，图片将会根据用户的屏幕尺寸自动调整图像大小，更方便去做各个屏幕的适配。另外Bootstrap 还提供了很多额外的工具类辅助进行网页开发。
*   Bootstrap框架提供的组件、插件、布局、栅格系统、响应式工具等等，可以为节省了大量的开发时间。

**缺点**

*   不适合高度定制类型的项目，因为Bootstrap具有统一的视觉风格，高度定制类的项目需要大量的自定义和样式覆盖。
*   Bootstrap的框架文件比较大(61KB JS + 159KB CSS)，资源文件过大会增加网站首屏加载的时间，并加重服务器的负担。
*   Bootstrap样式相对笨重，也会额外添加一些不必要的HTML元素，他会浪费一小部分浏览器的资源。

总结：Bootstrap很容易上手，并且也有非常完整的中文文档；Bootstrap使用 jQuery 与HTML 交互。对于初学者来说，它将是一个不错的入门方式。 同时Bootstrap框架优秀的设计和架构思想也是非常值得学习。

  

2_Bootstrap4的安装
---------------

Bootstrap 是一个前端框架。

*   该框架主要是由CSS 和 JS组成，但是也会依赖一小部分的HTML。
*   因此在安装Bootstrap时，-需要引入相应的CSS和JS文件，当然也需要添加一些全局的配置。
*   在Bootstrap 5 版本以前，Bootstrap是依赖jQuery的。
*   那么如果使用的是Bootstrap5以下的版本，需在引入Bootstrap之前先引入jQuery库。

Bootstrap的内容组成，不同的下载文件，包含的内容也不一样

![在这里插入图片描述](https://img-blog.csdnimg.cn/a970bb39b25342d5a39972f63244341d.jpeg#pic_center)

### 2.1_方式一 CDN

Bootstrap框架的CDN地址

*   https://cdn.jsdelivr.net/npm/bootstrap@4.6.1/dist/css/bootstrap.min.css
*   https://cdn.jsdelivr.net/npm/jquery@3.5.1/dist/jquery.slim.min.js
*   https://cdn.jsdelivr.net/npm/bootstrap@4.6.1/dist/js/bootstrap.bundle.min.js

HTML中引入之后，添加重要的全局配置

*   HTML5 文档类型（doctype 或 DOCTYPE），Bootstrap 要求文档类型（doctype）是 HTML5。 如果没有设置这个，就会看到一些古怪的、不完整的样式，因此，正确设置文档类型（doctype）能轻松避免这些困扰。

    <!DOCTYPE html>
    

*   添加视口（viewport）
    
    *   Bootstrap 采用的是移动设备优先（mobile first） 的开发策略，为了网页能够适配移动端的设备，需在 `<head>` 标签中添加viewport（视口）。
        
    *   在移动端会把 layout viewport 的宽度设置为设备的宽，并且不允许用户进行页面的缩放。
        

    <meta name="viewport" content="width=device-width, initial-scale=1.0,user-scalable=no,maximum-scale=1.0,minimum-scale=1.0,shrink-to-fit=no">
    

  

示例：

    <!DOCTYPE html>
    <html lang="en">
    <head>
      <meta charset="UTF-8">
      <meta http-equiv="X-UA-Compatible" content="IE=edge">
      <!-- safari 9+ -->
      <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no, minimum-scale=1.0, maximum-scale=1.0, shrink-to-fit=no">
      <title>Document</title>
      <!-- 引入Bootstrap框架中的CSS文件: box-size:border-box -->
      <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.6.1/dist/css/bootstrap.min.css">
    </head>
    <body>
    
      <h1 class="text-left border border-primary">Hello Bootstrap</h1>
    
      <!-- Bootstrap5 之前需要依赖jQuery库 ，故需要引入JQ库-->
      <script src="https://cdn.jsdelivr.net/npm/jquery@3.5.1/dist/jquery.slim.min.js"></script>
      <!-- 引入Bootstrap的JS文件 -->
      <script src="https://cdn.jsdelivr.net/npm/bootstrap@4.6.1/dist/js/bootstrap.bundle.min.js"></script>
    </body>
    </html>
    

  

### 2.2_方式二 : 下载源码引入

Bootstrap框架的下载

*   Bootstrap下载地址：https://v4.bootcss.com/docs/getting-started/download/
*   jQuery下载地址：https://jquery.com/download/

添加重要的全局配置

*   HTML5 文档类型（doctype 或 DOCTYPE），Bootstrap 要求文档类型（doctype）是 HTML5。
*   添加视口viewport（shrink-to-fit 是为了兼容 Safari 9 以后版本，禁止页面的伸缩)
*   integrity: 防止资源被篡改，篡改了将不加载；crossorigin：加载不同源的资源时，是否需要需带用户凭证（cook)

    <!DOCTYPE html>
    <html lang="en">
    <head>
      <meta charset="UTF-8">
      <meta http-equiv="X-UA-Compatible" content="IE=edge">
      <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no, minimum-scale=1.0, maximum-scale=1.0, shrink-to-fit=no">
      <title>Document</title>
      <!-- 引入 Bootstarp中的CSS文件 -->
      <link rel="stylesheet" href="../libs/bootstrap-4.6.1/css/bootstrap.css">
    </head>
    <body>
      
    
      <h1 class="float-right">hello Bootstrap</h1>
    
      <script src="../libs/jquery/jquery-3.6.0.js"></script>
      <!-- bundle.js分成下面两部分
        popper.js
        bootstrap.js
       -->
      <script src="../libs/bootstrap-4.6.1/js/bootstrap.bundle.js"></script>
    </body>
    </html>
    

  

### 2.3_方式三 : npm安装

![在这里插入图片描述](https://img-blog.csdnimg.cn/61f72a5492d74d69ad1e7c2e6a08e9c6.jpeg#pic_center)

  

3_Bootstrap初体验
--------------

需求：开发两个按钮，一个天空蓝的按钮和一个橙色的按钮。  
下面将使用两种方式实现：  
(1) 用CSS来开发

    <style>
    .btn{
      width: 60px;
      line-height: 40px;
      color: white;
      text-align: center;
    }
    
    .btn-cirlce{
      border-radius: 4px;
    }
    
    .btn-primary{
      background-color: skyblue;
    }
    
    .btn-warning{
      background-color: orange;
    }
    .btn-default{
      background-color: #cdcdcd;
    }
    
    </style>
    
    <body>
      <div class="btn btn-cirlce btn-primary">按钮1</div>
      <div class="btn btn-cirlce btn-warning">按钮2</div>
      <div class="btn btn-cirlce btn-default">按钮2</div>
    </body>
    

(2) 用Bootstrap框架

      <!-- 引入 Bootstarp中的CSS文件 -->
      <link rel="stylesheet" href="../libs/bootstrap-4.6.1/css/bootstrap.css">
    
    <body>
      //只需添加对应的类名，即可实现样式
      <div class="btn btn-primary">按钮1</div>
      <div class="btn btn-warning">按钮2</div>
      <button class="btn btn-info">按钮3</button>
       //引入jQ库文件
      <script src="../libs/jquery/jquery-3.6.0.js"></script>
       //引入Bootstap的JS文件 
      <script src="../libs/bootstrap-4.6.1/js/bootstrap.bundle.js"></script>
    </body>
    

  

补充：Bootstrap4 框架设计图

![在这里插入图片描述](https://img-blog.csdnimg.cn/ae33732a1ca04e39ad2c0c6199603a1a.jpeg#pic_center)

  

4_响应式容器原理
---------

### 4.1_屏幕尺寸的分割点（Breakpoints）

*   Bootstrap的一大核心就是响应式，即开发一套系统便可以适配不同尺寸的屏幕。它底层原理是使用媒体查询来为布局和页面创建合理的断点(Breakpoints)，然后根据这些合理的断点来给不同尺寸屏幕应用不同的CSS样式。
*   Bootstrap 4设了5个断点来构建响应式系统，5个断点分别为 Extra-Small、Small、Medium、Large、Extra large
*   媒体查询是CSS的一项功能，它允许你根据浏览器的分辨率来应用不同的CSS样式，如 @media (min-width: 576px){}

![在这里插入图片描述](https://img-blog.csdnimg.cn/7971bf240a2e4688b87e7702f6680ca1.png#pic_center)

  

### 4.2_响应式容器Containers

Containers容器是 Bootstrap中最基本的布局元素，并且该布局支持响应式。在使用默认网格系统时是必需的。

Containers容器用于包含、填充，有时也会作为内容居中使用。容器也是可以嵌套，但大多数布局不需要嵌套容器。

Bootstrap 带有三个不同的Containers容器：

*   `.container`: 它在每个断点处会设置不同的max-width。
*   `.container-fluid`：在所有断点处都是 width: 100%。
*   `.container-{breakpoint},` 默认是width: 100%，直到指定断点才会修改为响应的值。

![在这里插入图片描述](https://img-blog.csdnimg.cn/6b4e6324b87648c4bbec2a9af72fc68e.jpeg#pic_center)

  

5_网格系统（Grid system）
-------------------

### 5.1_认识

在开发一个页面时，经常会遇到一些列表（例如，商品列表），这些列表通常都是通过行和列来排版。

*   对于这种列表-可以使用float来实现，也可以使用flexbox布局实现。
*   为了方便-对这种常见列表的布局，Bootstrap框架对它进行了封装，封装为一个网格系统（Grid system）。

网格系统是什么？

*   Bootstrap网格系统是用于构建移动设备优先的强大布局系统，可支持12列网格、5 个断点和数十个预定义类。
*   提供了一种简单而强大的方法来创建各种形状和大小的响应式布局。
*   底层使用了强大的flexbox来构建弹性布局，并支持12列的网格布局。
*   网格系统是使用container、row和col类来布局，并且布局是支持响应的。

如何使用网格系统？

*   编写一个container或container-fluid容器；
*   在container容器中编写row容器；
*   在row容器中编写列col容器。

比如，使用Boostrap来实现一行3列的布局。

      <!-- 引入 Bootstarp中的CSS文件 -->
      <link rel="stylesheet" href="../libs/bootstrap-4.6.1/css/bootstrap.css">
      <style>
        .container{
          background-color: pink;
        }
        .item{
          height: 40px;
          border: 1px solid red;
        }
      </style>
    
    <body>
       <div class="container">
        <!-- 【其类名的实际css样式如下】
          display: flex
          flex-wrap:wrap
         -->
         <div class="row">
          <!-- 【其类名的实际css样式如下】
            flex item:   flex-grow: 1
           -->
           <div class="col item">1</div>
           <div class="col item">2</div>
           <div class="col item">3</div>
         </div>
    
       </div>
    </body>
    

  

### 5.2_12列网格系统

从Bootstrap2开始，网格系统从16 列转向12列网格，原因之一是12列比以前的16列系统更灵活。

将一个容器(row)被划分为12列网格，具有更广泛的应用，因为 12 可以被 12、6、4、3、2 、1整除，而 16列网格只能被 16、8、4 、2、1 整除，所以12列网格能够在一行中表示更多种列数组合情况。

12列网格这意味着可将一行分解为12、6、4、3、2和1份：

*   1列，独占12等份
*   2列，每列占6等份
*   3列，每列占4等份
*   4列，每列占3等份。
*   6列，每列占2等份
*   12列，每列占1等份

  

### 5.3_网格系统的原理

网格系统是有container、row、col三部分组成，底层使用flexbox来布局，并且支持12列网格布局。

`container`或`container-fluid`是布局容器，网格系统中必用的容器（该容器也会应用在：内容居中或作为包含其它内容等）。

*   width: 100% / 某个断点的宽; - 布局的宽
*   padding-right: 15px; - 让包含的内容不会靠在布局右边缘
*   padding-left: 15px; - 让包含的内容不会靠在布局左边缘
*   margin-right: auto; - 布局居中
*   margin-left: auto; - 布局居中

`row`是网格系统中的每一行，row是存放在container容器中。如果指定列宽，那么一行最多可以存放12列，超出列数会换行。

*   display: flex; - 指定row为弹性布局（并支持12列网格布局）
*   flex-wrap: wrap; - 支持多行展示flex item。
*   margin-right: -15px; - 抵消container右边15px的padding
*   margin-left: -15px; - 抵消container左边15px的padding。

【row左右-15px的外边距margin，是用来抵消container容器15px内边距，实现row左右边缘和容器左右边缘对齐。可以理解为复制粘贴，大小尺寸一模一样】

`col`是网格系统的每一列，col是存放在row容器中

*   position: relative; - 相对定位布局
*   flex-grow: 1 / flex:0 0 x%; - 自动拉伸布局或占百分比
*   max-width: 100% / max-width: x%; - 最大的宽
*   padding-right: 15px; - 让包含内容不会靠右边缘
*   padding-left: 15px; - 让包含内容不会靠左边缘。

  

### 5.4_嵌套(nesting)

Bootstrap的网格系统是可以支持嵌套的，例如：

*   可以在某个网格系统的某一列上继续嵌套一个网格系统。
*   当网格系统中的某一列嵌套一个网格系统的时候，嵌套的网络系统可以省略container容器。
*   因为网格系统中的col是可以充当一个container-fluid容器来使用（col的属性和container-fluid的属性基本一样）。

一个案例： 用指定列宽( 语法：col-{number} ) 的方式来实现一行8列的布局

      <link rel="stylesheet" href="../libs/bootstrap-4.6.1/css/bootstrap.css">
      <style>
        .container{
          background-color: pink;
        }
        .item{
          height: 40px;
          border: 1px solid red;
        }
      </style>
    
    <body>
        <!--     方式一  flex:列宽是自动拉伸，并且每列的宽度是相等的【等列宽】 -->
       <div class="container">
        <div class="row">
          <div class="col item">1</div>
          <div class="col item">2</div>
          <div class="col item">3</div>
          <div class="col item">4</div>
          <div class="col item">5</div>
          <div class="col item">6</div>
          <div class="col item">7</div>
          <div class="col item">8</div>
        </div>
       </div>
       <!-- 方式二: 指定列宽 -->
       <div class="container">
        <div class="row">
          <div class="col-6 item">  
            <!-- 嵌套网格系统( 嵌套的时候是可以省略container ) -->
            <div class="row">
               <div class="col-3 item">1</div>
               <div class="col-3 item">2</div>
               <div class="col-3 item">3</div>
               <div class="col-3 item">4</div>
            </div>
          </div>
          <div class="col-6 item">
            <!-- ( 嵌套的时候是可以省略container ) -->
            <div class="row">
              <div class="col-3 item">1</div>
              <div class="col-3 item">2</div>
              <div class="col-3 item">3</div>
              <div class="col-3 item">4</div>
            </div>
          </div>
        </div>
       </div>
    </body>
    

  

### 5.5_自动布局（Auto-layout ）

`col` : **等列宽**（Equal-width）。 底层代码是 flex-grow: 1, max-width: 100%。该类网格系统仅用flexbox布局。

【可以理解为，每行的每个元素宽度相等，总宽度被平分】

        <link rel="stylesheet" href="../libs/bootstrap-4.6.1/css/bootstrap.css">
      <style>
    
        .container{
          background-color: pink;
        }
        .item{
          height: 40px;
          border: 1px solid red;
        }
      </style>
      <body>
      <!-- 网格系统-等列宽- flex-grow:1   -->
      <div class="container">
        <div class="row">
          <div class="col item">1</div>
          <div class="col item">2</div>
          <div class="col item">3</div>
          <div class="col item">4</div>
          <div class="col item">5</div>
          <div class="col item">6</div>
          <div class="col item">7</div>
          <div class="col item">8</div>
          <div class="col item">9</div>
          <div class="col item">10</div>
          <div class="col item">11</div>
          <div class="col item">12</div>
          <div class="col item">13</div>
          <div class="col item">13</div>
          <div class="col item">13</div>
          <div class="col item">13</div>
          <div class="col item">13</div>
          <div class="col item">13</div>
          <div class="col item">13</div>
        </div>
      </div>
    </body>  
    

`col-auto` : 列的宽为auto ，**自动列宽**，随着填充内容的大小变化 。其底层代码是 flex: 0 0 auto; width: auto

      <!-- 网格系统-等列宽- flex-grow:1   -->
      <div class="container">
        <div class="row">
          <!-- 随着内容的宽度变化。 其余等列宽度均分 =（总宽度-自动列宽）/剩余列的数量-->
          <div class="col-auto item">auto layout  layout layout </div>  
          <div class="col item">1</div>
          <div class="col item">2</div>
          <div class="col item">3</div>
        </div>
      </div>
    

`col-{num}`: 指定某个列的宽（支持12列网格） 其底层代码是 flex: 0 0 x%，max-width: x%。

num的范围是1~12。比如说，col-2，意味着，这个元素的宽度占这一行宽度的2/12，也就是1/6.

        <!-- 网格系统-等列宽- flex-grow:1   -->
      <div class="container">
        <div class="row">
          <!--  flex: 0 0 xx%;  超过12列就会自动换行，可以理解为分子累加超过12-->
          <div class="col-1 item">1/12</div>
          <div class="col-2 item">2/12</div>
          <div class="col-3 item">3/12</div>
          <div class="col-6 item">6/12</div>
          <div class="col-1 item">1/12</div>
          <div class="col-1 item">1/12</div>
          <div class="col-1 item">1/12</div>      
        </div>
    
        <div class="row">
          <!--         flex: 0 0 xx%;       -->
          <div class="col-1 item">1/12</div>
          <div class="col-2 item">2/12</div>
          <div class="col-3 item">3/12</div>
          <div class="col-6 item">6/12</div>
        </div>
      </div>
    

运行效果如下图

![在这里插入图片描述](https://img-blog.csdnimg.cn/b9691b6a8e0c431886f80ac04452517b.jpeg#pic_center)

  

### 5.7_响应式类（Responsive Class）

5个断点(Breakpoints) ： none(xs) : <576px 、sm : >=576px、 md : >=768px、 lg : >=992、 xl : >=1200px

响应式列布局的类

*   col-sm : 默认 width:100%，当屏幕>=576px该类启用（flexbox布局）, 启用： flex-grow: 1，max-width: 100%。
*   col-md: 默认 width:100%，当屏幕>=768px该类启用（flexbox布局），启用： flex-grow: 1，max-width: 100%。
*   col-lg : 默认 width:100%，当屏幕>=992px该类启用（flexbox布局），启用： flex-grow: 1，max-width: 100%。
*   col-xl : 默认 width:100%，当屏幕>=1200px该类启用（flexbox布局）, 启用： flex-grow: 1，max-width: 100%。
*   col-sm-{num} : 默认 width:100%，当屏幕>=576px该类启用 (支持12列网格), 启用： flex: 0 0 x%。
*   col-md-{num} : 默认 width:100%，当屏幕>=768px该类启用 (支持12列网格), 启用： flex: 0 0 x%。
*   col-lg-{num} : 默认 width:100%，当屏幕>=992px该类启用 (支持12列网格), 启用： flex: 0 0 x%。
*   col-xl-{num} : 默认 width:100%，当屏幕>=1200px该类启用 (支持12列网格) , 启用： flex: 0 0 x%。

比如一个需求：开发响应式列表，xl屏幕显示6列，在lg屏幕显示4列，在md屏幕显示3列，在sm屏幕显示2列，特小屏(none)显示1列。

      <!-- 网格系统 -->
      <div class="container">
        <div class="row">      
          <div class="col-12 col-sm-6 col-md-4 col-lg-3 col-xl-2 item">1</div>
          <div class="col-12 col-sm-6 col-md-4 col-lg-3 col-xl-2 item">2</div>
          <div class="col-12 col-sm-6 col-md-4 col-lg-3 col-xl-2 item">3</div>
          <div class="col-12 col-sm-6 col-md-4 col-lg-3 col-xl-2 item">4</div>
          <div class="col-12 col-sm-6 col-md-4 col-lg-3 col-xl-2 item">5</div>
          <div class="col-12 col-sm-6 col-md-4 col-lg-3 col-xl-2 item">6</div>
        </div>
      </div>
    

  

6_响应式工具类
--------

### 6.1_认识

在开发响应式页面时，可能会有这样的需求：

*   某个功能在PC端可见，但是在移动端不可见。
*   因为移动端的屏幕比较小，是不能把PC端中所有的内容都展示出来，所以有些不重要的内容可能在移动端就被简化了
*   这时就可以借用响应式的工具来实现该功能。

Bootstrap的响应式工具类-Display

*   为了更快地进行多端的开发，可以使用Bootstrap提供的响应式工具类（display），该类可按设备显示和隐藏元素。
*   为了避免为同一个网站开发出多个不同的版本（PC、iPad、iPhone），可以针对每个屏幕尺寸响应地隐藏和显示元素，来实现在不同屏幕上显示不同的页面。

如何使用响应工具类（display）?

*   隐藏元素可以给某个元素添加 .d-none 类或 .d-{sm,md,lg,xl,xxl}-none 类中的任何一个。
*   显示元素可以给某个元素添加 .d-block 类或 .d-{sm,md,lg,xl,xxl}-block 类中的任何一个

  

### 6.2_响应式工具类-Display

不同作用的类名

![在这里插入图片描述](https://img-blog.csdnimg.cn/df124e4a807b4a24a4ebd723b702a431.jpeg#pic_center)

需求实现：

*   某个元素只在lg(>=992px) 和 xl 屏显示；（大于xl的同时也大于lg，故只需去掉d-xl-non即可e

     <h1 class="d-none d-lg-block">某个元素只在lg(>=992px) 和 xl 屏显示</h1>
      <!-- 理解为，这个元素本身是隐藏的，然后屏幕分辨率满足lg、xl条件时显示 -->
    

*   某个元素只在lg(>=992px) 和 xl 屏隐藏；

    <h1 class="d-block d-lg-none">某个元素只在lg(>=992px) 和 xl 屏隐藏</h1>
      <!-- 理解为，这个元素本身是显示的，然后屏幕分辨率满足lg、xl条件时隐藏 -->
    

*   某个元素只在 md(>=768px) 屏隐藏；

      <h1 class="d-block d-md-none d-lg-block">某个元素只在 md(>=768px) 屏隐藏；</h1>
      <!-- 理解为，这个元素本身是显示的，然后屏幕分辨率满足md条件时隐藏 -->
    

  

### 6.3_实用的工具类（Utility classes）

快速浮动（Float）

*   float-left
*   float-right

文本（Text）

*   text-left、text-right、text-center
*   text-{sm、md、lg、xl}-left

边框

*   borde border-top border-left …
*   border border-primary border-success

截断文本 ： text-truncate

  

### 6.4_可访问性-辅助类（了解）

屏幕阅读器的适配（专门针对残障人士设备的适配）

*   .sr-only ： .sr-only 类可以对屏幕阅读器以外的设备隐藏内容，即对屏幕阅读辅助器可见。
*   .sr-only-focusable ： .sr-only 和 .sr-only-focusable 联合使用的话可以在元素有焦点的时候再次显示出来（例如，使用键盘导航的用户）。对于需遵循可访问性的网站来说是很有必要的。

增强可访问性的辅助类（针对残障人使用的设备的适配，同时增强语义化）

*   role=”xxx” : 定义用户界面元素的类型，作用增强Web可访问性，使残障人士可以更好的使用Web内容。
*   aria-*=”xxx”: 增强可访问性，当与role=“xxx”结合使用时，当元素的状态和属性发生变化时会触发辅助技术发出通知，并将信息传达给用户

  

7_Bootstrap组件
-------------

访问官网 https://getbootstrap.com/docs/5.3/components/accordion/

可以复制其中的组件代码体验，前提是安装好Bootstrap

  

8_项目
----

前提，导入Bootstrap库以及JQ库。

效果图如下

![在这里插入图片描述](https://img-blog.csdnimg.cn/8f7480b5fef0479abbd746244caba304.png#pic_center)  
  

![在这里插入图片描述](https://img-blog.csdnimg.cn/7762c073477648edb5eb828af2f6aead.png#pic_center)  
  

### 8.1_导航栏

      <!-- 1.导航栏 -->
      <nav class="navbar navbar-expand-lg">
       
        <div class="container-fluid">
          <!-- logo -->
          <a class="navbar-brand" href="#">
            <img class="logo" src="./img/logo.png" alt="">
          </a>
          
          <!-- 按钮 <=992才会显示出来  -->
          <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav">
            <img class="expand-icon" src="./img/show-icon.png" alt="">
          </button>
          
          <!-- 导航列表 -->
          <div class="collapse navbar-collapse" id="navbarNav">
            <ul class="navbar-nav mr-auto">
              <!-- 使用自定义的样式 -->
              <li class="text-link active">
               <span>首页</span>
              </li>
              <li class="text-link">
                <span>API</span>
              </li>
              <li class="text-link">
                <span>解决方案</span>
              </li>
              <li class="text-link">
                <span>案例</span>
              </li>
              <li class="text-link">
                <span>新闻</span>
              </li>
              <li class="text-link">
                <span>关于我们</span>
              </li>
            </ul>
            <p class="text-link hot-line">
              <span>咨询热线：4009910008</span>
            </p>
          </div>
          
        </div>
      </nav>
    

  

### 8.2_轮播图

HTML代码

      <!-- 2.轮播图 -->
      <!--      data-ride="carousel" 当页面加载完成之后 录播图自动轮播   -->
      <div id="carouselExampleIndicators_liujun" class="carousel slide">
        <!-- 指示器 -->
        <ol class="carousel-indicators">
          <li data-target="#carouselExampleIndicators_liujun" data-slide-to="0" class="active"></li>
          <li data-target="#carouselExampleIndicators_liujun" data-slide-to="1"></li>
          <li data-target="#carouselExampleIndicators_liujun" data-slide-to="2"></li>
        </ol>
    
        <!-- 轮播图的图片 -->
        <div class="carousel-inner">
          <!-- 改为js动态加载图片        
          <div class="carousel-item active">
            <img src="./img/banner0.png" class="d-block w-100" alt="...">
          </div>
          <div class="carousel-item">
            <img src="./img/banner1.png" class="d-block w-100" alt="...">
          </div>
          <div class="carousel-item">
            <img src="./img/banner2.png" class="d-block w-100" alt="...">
          </div> 
        -->
        </div>
    
        <!-- 分页:上一张 下一张 -->
        <button class="carousel-control-prev" type="button" data-target="#carouselExampleIndicators_liujun" data-slide="prev">
          <span class="carousel-control-prev-icon"></span>
        </button>
        <button class="carousel-control-next" type="button" data-target="#carouselExampleIndicators_liujun" data-slide="next">
          <span class="carousel-control-next-icon"></span>
        </button>
      </div>
    

JS代码

    $(function() {
    
      var currentImg = 'none' // none  big  small
      // 1.准备数据
      var banners = [
        {
          id:0,
          bigUrl: './img/banner0.png',
          smUrl: './img/banner0_sm.png'
        },
        {
          id:0,
          bigUrl: './img/banner1.png',
          smUrl: './img/banner1_sm.png'
        },
        {
          id:0,
          bigUrl: './img/banner2.png',
          smUrl: './img/banner2_sm.png'
        }
      ]
    
      // renderBanner(banners)
    //加入了之前写的节流函数
      $(window).on('resize',throttle( function() {
        // console.log( $(this).outerWidth() )  // border + paddig + content 
        var winWidth =  $(this).outerWidth()
        var isBigScreen = winWidth >= 768
        if(currentImg === 'none'){
          // 调取这个函数来渲染界面
          renderBanner(banners, isBigScreen)
        }   
        if(currentImg === 'big' && !isBigScreen) {	//当前为大屏，要变为小屏
          renderBanner(banners, isBigScreen)
        }
        if(currentImg === 'small' && isBigScreen) {	//当前为小屏，要变为大屏
          renderBanner(banners, isBigScreen)
        }
        
      }))
      $(window).trigger('resize')
    
    
      function renderBanner(banners = [], isBigScreen) {
        currentImg = isBigScreen ? 'big' : 'small' 
        // 先把之前的定时器停掉
        $('.carousel').carousel('dispose')
        var banneHtmlString = ''
        // 2.将数据渲染到页面上
        banners.forEach(function(item, index) {
          var active = index === 0 ? 'active' :''
          var imgUrl = isBigScreen ? item.bigUrl: item.smUrl
          banneHtmlString +=`
             <div class="carousel-item ${active}" data-interval="3000">
              <img src="${imgUrl}" class="d-block w-100" alt="...">
            </div>
          `
        })
        $('.carousel-inner').empty().append(banneHtmlString)
        // 自动录播( 开始一个定时器 )
        $('.carousel').carousel('cycle')
      }
    
    })
    

  

补充：节流函数代码

      
      function throttle(fn, interval = 400, options = { leading: true, trailing: true }) {
        // 1.记录上一次的开始时间
        const { leading, trailing } = options
        let lastTime = 0
        let timer = null
      
        // 2.事件触发时, 真正执行的函数
        const _throttle = function(...args) {
      
          // 2.1.获取当前事件触发时的时间
          const nowTime = new Date().getTime()
          if (!lastTime && !leading) lastTime = nowTime
      
          // 2.2.使用当前触发的时间和之前的时间间隔以及上一次开始的时间, 计算出还剩余多长事件需要去触发函数
          const remainTime = interval - (nowTime - lastTime)
          if (remainTime <= 0) {
            if (timer) {
              clearTimeout(timer)
              timer = null
            }
      
            // 2.3.真正触发函数
            fn.apply(this, args)
            // 2.4.保留上次触发的时间
            lastTime = nowTime
            return
          }
      
          if (trailing && !timer) {
            timer = setTimeout(() => {
              timer = null
              lastTime = !leading ? 0: new Date().getTime()
              fn.apply(this, args)
            }, remainTime)
          }
        }
      
        return _throttle
      }
    

  

### 8.3_目标客户 版块

HTML代码

      <!-- 3.目标客户 -->
      <div class="target-customer">
        <!-- 在小屏上是不可见 -->
        <h1 class="title text-center d-none d-md-block">目标客户</h1>
        <!-- 网格系统性 -->
        <div class="container-fluid">
          <div class="row">
            <div class="col-md-6 col-xl-3 item">
              <img class=" d-none d-md-block" src="./img/target-1.png" alt="">
              <div class="sub-title">电子银行</div>
              <div class="desc text-center">
                <p>助力五大行、商业银行、城商行、农商行、农信社等</p>
                <p>手机银行与直销银行APP消费场景升级</p>
              </div>
            </div>
            <div class="col-md-6 col-xl-3 item">
              <!-- 在小屏上是不可见 -->
              <img class=" d-none d-md-block" src="./img/target-2.png" alt="">
              <div class="sub-title">金服平台</div>
              <div class="desc text-center">
                <p>助力钱包、小贷、基金、保险、信托、证券等</p>
                <p>金融服务平台APP 消费场景升级</p>
              </div>
            </div>
            <div class="col-md-6 col-xl-3 item">
              <img class=" d-none d-md-block" src="./img/target-3.png" alt="">
              <div class="sub-title">企业福利</div>
              <div class="desc text-center">
                <p>助力国有、私营、外资、人力资源公司等</p>
                <p>企业报销与福利系统消费场景升级</p>
              </div>
            </div>
            <div class="col-md-6 col-xl-3 item">
              <img class=" d-none d-md-block" src="./img/target-4.png" alt="">
              <div class="sub-title">智能终端</div>
              <div class="desc text-center">
                <p>助力机器人、汽车中控、电子屏、商用电视等</p>
                <p>人工智能语音消费场景升级</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    

  

CSS代码。因为bootstrap没有符合的，所以定制

    .target-customer{
      min-height: 265px;
      background-color: var(--bg-target-color);
    }
    
    .target-customer .title{
      height: 80px;
      line-height: 80px;
    
      font-size: 30px;
      color: var(--title-color);
      font-weight: normal;
    }
    
    .target-customer .row .item{
      display: flex;
      justify-content: center;
      align-items: center;
    
      height: 135px;
      cursor: pointer;
    
      overflow: hidden;
     
    }
    
    .target-customer .sub-title{
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
    
      font-size: 24px;
      color: var(--title-color);
      transition: top 0.6s ease;
    }
    
    .target-customer .desc{
      position: absolute;
      top: 125%;
      left: 50%;
      width: 100%;
      opacity: 0;
      transform: translate(-50%, -50%);
      transition: top 0.6s ease;
    }
    
    @media (min-width: 768px){
    
      .target-customer .row .item:hover .sub-title{
        top: 35%;
      }
      .target-customer .row .item:hover .desc{
        top: 73%;
        opacity: 1;
      }
    
    
    }
    
    @media (max-width: 768px){
      .target-customer .sub-title{
        top: 40%;
        font-size: 16px;
      }
      .target-customer .desc{
        top: 75%;
        opacity: 1;
        font-size: 14px;
      }
    
      .target-customer .row .item:nth-child(odd){
        background-color: white;
      }
    
      .target-customer .row .item:nth-child(even){
        background-color: var(--bg-target-color);
      }
    
    }
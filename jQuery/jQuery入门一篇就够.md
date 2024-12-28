 

#### 目录

*   [第一章 jQuery简介](#_jQuery_7)
*   *   [1.1、jQuery简介](#11jQuery_9)
    *   [1.2、jQuery官网](#12jQuery_13)
    *   [1.3、jQuery版本介绍](#13jQuery_19)
    *   [1.4、jQuery引入方式](#14jQuery_32)
    *   [1.5、jQuery快速使用](#15jQuery_50)
    *   [1.6、jQuery两把利器](#16jQuery_72)
*   [第二章 jQuery核心函数](#_jQuery_79)
*   *   [2.1、选择器](#21_81)
    *   *   [2.1.1、基本选择器](#211_83)
        *   *   [2.1.1.1、标签选择器](#2111_85)
            *   [2.1.1.2、id选择器](#2112id_101)
            *   [2.1.1.3、class选择器](#2113class_117)
            *   [2.1.1.4、通配符选择器](#2114_133)
            *   [2.1.1.5、并集选择器](#2115_151)
            *   [2.1.1.6、交集选择器](#2116_168)
        *   [2.1.2、层级选择器](#212_187)
        *   *   [2.1.2.1、子代选择器](#2121_189)
            *   [2.1.2.2、后代选择器](#2122_209)
            *   [2.1.2.3、兄弟选择器](#2123_229)
        *   [2.1.3、过滤选择器](#213_267)
        *   *   [2.1.3.1、基本筛选器](#2131_269)
            *   [2.1.3.2、内容筛选器](#2132_407)
            *   [2.1.3.3、属性筛选器](#2133_477)
            *   [2.1.3.4、可见性筛选器](#2134_593)
            *   [2.1.3.5、子元素筛选器](#2135_621)
        *   [2.1.4、表单选择器](#214_674)
        *   *   [2.1.4.1、表单类型选择器](#2141_676)
            *   [2.1.4.2、表单状态选择器](#2142_718)
    *   [2.2、工具](#22_743)
    *   *   [2.2.1、$.each方法](#221each_745)
        *   [2.2.2、$.trim方法](#222trim_775)
        *   [2.2.3、$.type方法](#223type_788)
        *   [2.2.4、$.isArray方法](#224isArray_801)
        *   [2.2.5、$.isFunction方法](#225isFunction_814)
    *   [2.3、ajax](#23ajax_829)
    *   *   [2.3.1、$.ajax方法](#231ajax_831)
        *   [2.3.2、$.get方法](#232get_875)
        *   [2.3.3、$.post方法](#233post_896)
*   [第三章 jQuery核心对象](#_jQuery_917)
*   *   [3.1、属性](#31_919)
    *   *   [3.1.1、属性](#311_921)
        *   *   [3.1.1.1、attr()](#3111attr_923)
            *   [3.1.1.2、prop()](#3112prop_951)
            *   [3.1.1.3、val()](#3113val_979)
        *   [3.1.2、样式](#312_1007)
        *   *   [3.1.2.1、css()](#3121css_1009)
            *   [3.1.2.2、addClass()](#3122addClass_1041)
            *   [3.1.2.3、removeClass()](#3123removeClass_1070)
            *   [3.1.2.4、hasClass()](#3124hasClass_1099)
            *   [3.1.2.5、toggleClass()](#3125toggleClass_1123)
        *   [3.1.3、尺寸](#313_1152)
        *   *   [3.1.3.1、width()](#3131width_1154)
            *   [3.1.3.2、height()](#3132height_1158)
            *   [3.1.3.3、innerWidth()](#3133innerWidth_1162)
            *   [3.1.3.4、innerHeight()](#3134innerHeight_1166)
            *   [3.1.3.5、outerWidth()](#3135outerWidth_1170)
            *   [3.1.3.6、outerHeight()](#3136outerHeight_1174)
            *   [3.1.3.7、综合演示](#3137_1178)
        *   [3.1.4、位置](#314_1205)
        *   *   [3.1.4.1、offset()](#3141offset_1207)
            *   [3.1.4.2、position()](#3142position_1232)
            *   [3.1.4.3、scrollLeft()](#3143scrollLeft_1271)
            *   [3.1.4.4、scrollTop()](#3144scrollTop_1294)
    *   [3.2、操作](#32_1317)
    *   *   [3.2.1、DOM内部插入](#321DOM_1319)
        *   *   [3.2.1.1、text()](#3211text_1321)
            *   [3.2.1.2、html()](#3212html_1349)
            *   [3.2.1.3、append()](#3213append_1378)
            *   [3.2.1.4、appendTo()](#3214appendTo_1398)
            *   [3.2.1.5、prepend()](#3215prepend_1418)
            *   [3.2.1.6、prependTo()](#3216prependTo_1438)
        *   [3.2.2、DOM外部插入](#322DOM_1458)
        *   *   [3.2.2.1、after()](#3221after_1460)
            *   [3.2.2.2、before()](#3222before_1477)
            *   [3.2.2.3、insertAfter()](#3223insertAfter_1494)
            *   [3.2.2.4、insertBefore()](#3224insertBefore_1511)
        *   [3.2.3、DOM移除](#323DOM_1528)
        *   *   [3.2.3.1、empty()](#3231empty_1530)
            *   [3.2.3.2、remove()](#3232remove_1552)
        *   [3.2.4、DOM替换](#324DOM_1576)
        *   *   [3.2.4.1、replaceWith()](#3241replaceWith_1578)
            *   [3.2.4.2、replaceAll()](#3242replaceAll_1598)
        *   [3.2.5、DOM拷贝](#325DOM_1618)
        *   *   [3.2.5.1、clone()](#3251clone_1620)
        *   [3.2.6、DOM遍历](#326DOM_1641)
        *   *   [3.2.6.1、parent()](#3261parent_1643)
            *   [3.2.6.2、children()](#3262children_1665)
            *   [3.2.6.3、prev()](#3263prev_1690)
            *   [3.2.6.4、prevAll()](#3264prevAll_1712)
            *   [3.2.6.5、next()](#3265next_1737)
            *   [3.2.6.6、nextAll()](#3266nextAll_1759)
            *   [3.2.6.7、siblings()](#3267siblings_1784)
    *   [3.3、遍历](#33_1809)
    *   *   [3.3.1、遍历](#331_1811)
        *   *   [3.3.1.1、each()](#3311each_1813)
        *   [3.3.2、筛选](#332_1837)
        *   *   [3.3.2.1、first()](#3321first_1839)
            *   [3.3.2.2、last()](#3322last_1859)
            *   [3.3.2.3、eq()](#3323eq_1879)
            *   [3.3.2.4、not()](#3324not_1901)
            *   [3.3.2.5、filter()](#3325filter_1922)
    *   [3.4、事件](#34_1944)
    *   *   [3.4.1、浏览器事件](#341_1946)
        *   *   [3.4.1.1、resize()](#3411resize_1948)
            *   [3.4.1.2、scroll()](#3412scroll_1962)
        *   [3.4.2、事件绑定](#342_1982)
        *   *   [3.4.2.1、on()](#3421on_1984)
            *   [3.4.2.2、off()](#3422off_2002)
        *   [3.4.3、事件委托](#343_2022)
        *   *   [3.4.3.1、delegate()](#3431delegate_2024)
            *   [3.4.3.2、undelegate()](#3432undelegate_2047)
        *   [3.4.4、事件对象](#344_2074)
        *   [3.4.5、表单事件](#345_2090)
        *   *   [3.4.5.1、focus()](#3451focus_2092)
            *   [3.4.5.2、blur()](#3452blur_2110)
            *   [3.4.5.3、change()](#3453change_2131)
            *   [3.4.5.4、select()](#3454select_2169)
            *   [3.4.5.5、submit()](#3455submit_2187)
        *   [3.4.6、鼠标事件](#346_2207)
        *   *   [3.4.6.1、click()](#3461click_2209)
            *   [3.4.6.2、dblclick()](#3462dblclick_2227)
            *   [3.4.6.3、mousedown()](#3463mousedown_2245)
            *   [3.4.6.4、mouseup()](#3464mouseup_2263)
            *   [3.4.6.5、mouseenter()](#3465mouseenter_2281)
            *   [3.4.6.6、mouseleave()](#3466mouseleave_2315)
            *   [3.4.6.7、mouseover()](#3467mouseover_2349)
            *   [3.4.6.8、mouseout()](#3468mouseout_2385)
            *   [3.4.6.9、mousemove()](#3469mousemove_2421)
            *   [3.4.6.10、hover()](#34610hover_2450)
        *   [3.4.7、键盘事件](#347_2478)
        *   *   [3.4.7.1、keydown()](#3471keydown_2480)
            *   [3.4.7.2、keyup()](#3472keyup_2498)
            *   [3.4.7.3、keypress()](#3473keypress_2516)
    *   [3.5、动画](#35_2534)
    *   *   [3.5.1、基础](#351_2536)
        *   *   [3.5.1.1、hide()](#3511hide_2538)
            *   [3.5.1.2、show()](#3512show_2563)
            *   [3.5.1.3、toggle()](#3513toggle_2588)
        *   [3.5.2、渐变](#352_2616)
        *   *   [3.5.2.1、fadeIn()](#3521fadeIn_2618)
            *   [3.5.2.2、fadeOut()](#3522fadeOut_2646)
            *   [3.5.2.3、fadeToggle()](#3523fadeToggle_2674)
        *   [3.5.3、滑动](#353_2702)
        *   *   [3.5.3.1、slideDown()](#3531slideDown_2704)
            *   [3.5.3.2、slideUp()](#3532slideUp_2732)
            *   [3.5.3.3、slideToggle()](#3533slideToggle_2760)
        *   [3.5.4、自定义](#354_2788)
        *   *   [3.5.4.1、animate()](#3541animate_2790)
            *   [3.5.4.2、stop()](#3542stop_2821)
*   [第四章 jQuery插件介绍](#_jQuery_2825)
*   *   [4.1、扩展jQuery工具](#41jQuery_2827)
    *   [4.2、扩展jQuery对象](#42jQuery_2868)
*   [第五章 jQuery项目百练](#_jQuery_2924)
*   *   [5.1、项目百练介绍](#51_2926)
    *   [5.2、项目百练目录](#52_2930)

* * *

**配套资料，免费下载**  
链接：https://pan.baidu.com/s/152NnFqzAUx9br2qb49mstA  
提取码：ujyp  
复制这段内容后打开百度网盘手机App，操作更方便哦

第一章 [jQuery](https://so.csdn.net/so/search?q=jQuery&spm=1001.2101.3001.7020)简介
------------------------------------------------------------------------------

### 1.1、jQuery简介

jQuery 是一个高效、精简并且功能丰富的 JavaScript 工具库。它提供的 API 易于使用且兼容众多浏览器，这让诸如 HTML 文档遍历和操作、事件处理、动画和 Ajax 操作更加简单。目前超过90%的网站都使用了jQuery库，jQuery的宗旨：写的更少，做得更多！

### 1.2、jQuery官网

官方地址：[点击打开](https://jquery.com/)

官方文档：[点击打开](https://api.jquery.com/)

### 1.3、jQuery版本介绍

*   **1.x** （本教程所采用）
    *   兼容老版本IE
    *   文件较大，但兼容性最好
*   **2.x**
    *   部分IE8及以下版本不支持
    *   文件较小，执行效率更高
*   **3.x**
    *   完全不再支持IE8及以下版本
    *   提供了一些新的API
    *   提供不包含AJAX/动画API的版本

### 1.4、jQuery引入方式

*   本地引入：将jQuery下载下来，然后导入项目中，使用script标签进行引用

    <head>
        <script src="jquery-1.9.1.min.js"></script>
    </head>    
    

*   CDN引入：使用远程CDN资源库在线引入，避免了文件下载（本教程所采用）

    <head>
        <script src="https://cdn.bootcdn.net/ajax/libs/jquery/1.9.1/jquery.min.js"></script>
    </head>    
    

### 1.5、jQuery快速使用

    <!DOCTYPE html>
    <html>
    <head>
        <meta charset="UTF-8">
        <title>jQuery</title>
    </head>
    <body>
    
    <script src="https://cdn.bootcdn.net/ajax/libs/jquery/1.9.1/jquery.min.js"></script>
    <script>
        $(function () {
            // 请将jQuery代码书写在这里 ...
            alert('Hello,World!');
        });
    </script>
    </body>
    </html>
    

### 1.6、jQuery两把利器

jQuery两把利器分别是：

*   jQuery核心函数：即： `$()` 或 jQuery()，jQuery定义了这个全局的函数供我们调用，它既可作为一般函数调用，且传递的参数类型不同/格式不同，功能就完全不同，也可作为对象调用其定义好的方法，此时 `$` 就是一个工具对象。
*   jQuery核心对象：即执行jQuery核心函数返回的对象，jQuery对象内部包含的是dom元素对象的伪数组(可能只有一个元素)，jQuery对象拥有很多有用的属性和方法，让程序员能方便的操作dom，调用jQuery对象的任何方法后返回的还是当前jQuery对象。

第二章 jQuery核心函数
--------------

### 2.1、[选择器](https://so.csdn.net/so/search?q=%E9%80%89%E6%8B%A9%E5%99%A8&spm=1001.2101.3001.7020)

#### 2.1.1、基本选择器

##### 2.1.1.1、标签选择器

**需求描述：选择页面中所有的div标签，设置其背景为红色**

    <div>我是div1</div>
    <div>我是div2</div>
    <div>我是div3</div>
    

    $('div').css('background', 'red');
    

![image-20201108173258243](https://img-blog.csdnimg.cn/img_convert/56589a375829ca74ad6d853871e02c84.png)

##### 2.1.1.2、id选择器

**需求描述：选择页面中所有id为btn的按钮，设置其背景为红色**

    <button>按钮1</button>
    <button id="btn">按钮2</button>
    <button>按钮3</button>
    

    $('#btn').css('background', 'red');
    

![image-20201108174241651](https://img-blog.csdnimg.cn/img_convert/2749f18b2260e2e773d903464eab8fe8.png)

##### 2.1.1.3、class选择器

**需求描述：选择页面中所有class为red的段落，设置其背景为红色**

    <p class="red">我是段落1</p>
    <p>我是段落2</p>
    <p class="red">我是段落3</p>
    

    $('.red').css('background', 'red');
    

![image-20201108174410579](https://img-blog.csdnimg.cn/img_convert/9161c78821b91eab58c096f09de9e982.png)

##### 2.1.1.4、通配符选择器

**需求描述：选择页面中class为content的div下所有元素，设置其背景为红色**

    <div class="content">
        <p>我是段落1</p>
        <p>我是段落2</p>
        <p>我是段落3</p>
    </div>
    

    $('.content *').css('background', 'red');
    

![image-20201108183707902](https://img-blog.csdnimg.cn/img_convert/62d67c6bab0c110cf545c07b46c9ccff.png)

##### 2.1.1.5、并集选择器

**需求描述：选择页面中所有的段落与按钮，设置其背景为红色**

    <p>我是段落</p>
    <button>我是按钮</button>
    <div>我是div</div>
    <h1>我是大标题</h1>
    

    $('p,button').css('background', 'red');
    

![image-20201108183914014](https://img-blog.csdnimg.cn/img_convert/f802df6d886921c4b81ea9f2cad23fe2.png)

##### 2.1.1.6、交集选择器

**需求描述：选择页面中所有class为red的段落，设置其背景为红色**

    <p class="red">我是段落1</p>
    <p class="red">我是段落2</p>
    <p class="red">我是段落3</p>
    <div class="red">我是div1</div>
    <div class="red">我是div2</div>
    <div class="red">我是div3</div>
    

    $('p.red').css('background', 'red');
    

![image-20201108184128559](https://img-blog.csdnimg.cn/img_convert/91171d1352c26805ba1133995f1df4ce.png)

#### 2.1.2、层级选择器

##### 2.1.2.1、子代选择器

**需求描述：选择ul下的所有span子元素，设置其背景为红色**

    <ul>
        <span>我是ul的span1</span>
        <li>我是li1 <span>我是li1的span1</span></li>
        <li>我是li2 <span>我是li2的span2</span></li>
        <li>我是li3 <span>我是li3的span3</span></li>
        <span>我是ul的span2</span>
    </ul>
    

    $('ul>span').css('background', 'red');
    

![image-20201110181100657](https://img-blog.csdnimg.cn/img_convert/19cba6d06b80b5044675ffeccb257701.png)

##### 2.1.2.2、后代选择器

**需求描述：选择ul下的所有span元素，设置其背景为红色**

    <ul>
        <span>我是ul的span1</span>
        <li>我是li1 <span>我是li1的span1</span></li>
        <li>我是li2 <span>我是li2的span2</span></li>
        <li>我是li3 <span>我是li3的span3</span></li>
        <span>我是ul的span2</span>
    </ul>
    

    $('ul span').css('background', 'red');
    

![image-20201110181202087](https://img-blog.csdnimg.cn/img_convert/52122f6dc6f4c3eb6bb5699af2e9629e.png)

##### 2.1.2.3、兄弟选择器

**需求描述：选中id为box的下一个兄弟li，设置其背景为红色**

    <ul>
        <span>我是ul的span1</span>
        <li id="box">我是li1 <span>我是li1的span1</span></li>
        <li>我是li2 <span>我是li2的span2</span></li>
        <li>我是li3 <span>我是li3的span3</span></li>
        <span>我是ul的span2</span>
    </ul>
    

    $('#box+li').css('background', 'red');
    

![image-20201110181745366](https://img-blog.csdnimg.cn/img_convert/145a312754b9668d871ed8ec081c5a24.png)

**需求描述：选中id为box的后边的兄弟li，设置其背景为红色**

    <ul>
        <span>我是ul的span1</span>
        <li id="box">我是li1 <span>我是li1的span1</span></li>
        <li>我是li2 <span>我是li2的span2</span></li>
        <li>我是li3 <span>我是li3的span3</span></li>
        <span>我是ul的span2</span>
    </ul>
    

    $('#box~li').css('background', 'red');
    

![image-20201110181831495](https://img-blog.csdnimg.cn/img_convert/ee09eaefeb3b186b1e349b46223a3508.png)

#### 2.1.3、过滤选择器

##### 2.1.3.1、基本筛选器

**需求描述：实现隔行变色，让表格的奇数行的背景变为红色，:even代表选取下标为偶数的行**

    <table cellspacing="0px" cellpadding="10px" border="1px">
        <tr><td>张三</td><td>男</td><td>21</td></tr>
        <tr><td>李四</td><td>女</td><td>22</td></tr>
        <tr><td>王五</td><td>男</td><td>23</td></tr>
        <tr><td>赵六</td><td>女</td><td>24</td></tr>
    </table>
    

    $('tr:even').css('background', 'red');
    

![image-20201111112357714](https://img-blog.csdnimg.cn/img_convert/45e60a4c0f7670fa1c3749f3998c2668.png)

**需求描述：实现隔行变色，让表格的偶数行的背景变为红色，:odd代表选取下标为奇数的行**

    <table cellspacing="0px" cellpadding="10px" border="1px">
        <tr><td>张三</td><td>男</td><td>21</td></tr>
        <tr><td>李四</td><td>女</td><td>22</td></tr>
        <tr><td>王五</td><td>男</td><td>23</td></tr>
        <tr><td>赵六</td><td>女</td><td>24</td></tr>
    </table>
    

    $('tr:odd').css('background', 'red');
    

![image-20201111112537833](https://img-blog.csdnimg.cn/img_convert/2cf7f0c378d877d1e23e52382329666e.png)

**需求描述：实现让表格的第一行的背景变为红色**

    <table cellspacing="0px" cellpadding="10px" border="1px">
        <tr><td>张三</td><td>男</td><td>21</td></tr>
        <tr><td>李四</td><td>女</td><td>22</td></tr>
        <tr><td>王五</td><td>男</td><td>23</td></tr>
        <tr><td>赵六</td><td>女</td><td>24</td></tr>
    </table>
    

    $('tr:first').css('background', 'red');
    

![image-20201111113400031](https://img-blog.csdnimg.cn/img_convert/b70a809c936f78f985aa3238137f2fab.png)

**需求描述：实现让表格的最后一行的背景变为红色**

    <table cellspacing="0px" cellpadding="10px" border="1px">
        <tr><td>张三</td><td>男</td><td>21</td></tr>
        <tr><td>李四</td><td>女</td><td>22</td></tr>
        <tr><td>王五</td><td>男</td><td>23</td></tr>
        <tr><td>赵六</td><td>女</td><td>24</td></tr>
    </table>
    

    $('tr:last').css('background', 'red');
    

![image-20201111113453734](https://img-blog.csdnimg.cn/img_convert/5bf609629b435993a76bdad550d00959.png)

**需求描述：实现让下标（从0开始）小于2的行数的背景变为红色**

    <table cellspacing="0px" cellpadding="10px" border="1px">
        <tr><td>张三</td><td>男</td><td>21</td></tr>
        <tr><td>李四</td><td>女</td><td>22</td></tr>
        <tr><td>王五</td><td>男</td><td>23</td></tr>
        <tr><td>赵六</td><td>女</td><td>24</td></tr>
    </table>
    

    $('tr:lt(2)').css('background', 'red');
    

![image-20201111113912067](https://img-blog.csdnimg.cn/img_convert/0fc796b9d3fa2bee46d5dbea3e60dd52.png)

**需求描述：实现让下标（从0开始）大于2的行数的背景变为红色**

    <table cellspacing="0px" cellpadding="10px" border="1px">
        <tr><td>张三</td><td>男</td><td>21</td></tr>
        <tr><td>李四</td><td>女</td><td>22</td></tr>
        <tr><td>王五</td><td>男</td><td>23</td></tr>
        <tr><td>赵六</td><td>女</td><td>24</td></tr>
    </table>
    

    $('tr:gt(2)').css('background', 'red');
    

![image-20201111114920024](https://img-blog.csdnimg.cn/img_convert/5fe33275c8930411ce7a0bf990716f12.png)

**需求描述：实现让下标（从0开始）等于2的行数的背景变为红色**

    <table cellspacing="0px" cellpadding="10px" border="1px">
        <tr><td>张三</td><td>男</td><td>21</td></tr>
        <tr><td>李四</td><td>女</td><td>22</td></tr>
        <tr><td>王五</td><td>男</td><td>23</td></tr>
        <tr><td>赵六</td><td>女</td><td>24</td></tr>
    </table>
    

    $('tr:eq(2)').css('background', 'red');
    

![image-20201111115028273](https://img-blog.csdnimg.cn/img_convert/db9fb2216c69b36879bed07761edc18f.png)

**需求描述：实现让下标（从0开始）不等于2的行数的背景变为红色**

    <table cellspacing="0px" cellpadding="10px" border="1px">
        <tr><td>张三</td><td>男</td><td>21</td></tr>
        <tr><td>李四</td><td>女</td><td>22</td></tr>
        <tr><td>王五</td><td>男</td><td>23</td></tr>
        <tr><td>赵六</td><td>女</td><td>24</td></tr>
    </table>
    

    $('tr:not(tr:eq(2))').css('background', 'red');
    

![image-20201111115202609](https://img-blog.csdnimg.cn/img_convert/0ca6ae085c410d10998fb5c3e9d4012c.png)

##### 2.1.3.2、内容筛选器

**需求描述：实现让内容为“男”的单元格的背景变为红色**

    <table cellspacing="0px" cellpadding="10px" border="1px">
        <tr><td>张三</td><td>男</td><td>21</td></tr>
        <tr><td>李四</td><td>女</td><td>22</td></tr>
        <tr><td>王五</td><td>男</td><td>23</td></tr>
        <tr><td>赵六</td><td>女</td><td>24</td></tr>
    </table>
    

    $('td:contains("男")').css('background', 'red');
    

![image-20201111120011180](https://img-blog.csdnimg.cn/img_convert/4106b5c666556ef9a4d1a1e04a0d9f35.png)

**需求描述：实现让内容为span标签的单元格的背景变为红色**

    <table cellspacing="0px" cellpadding="10px" border="1px">
        <tr><td>张三</td><td>男</td><td>21</td></tr>
        <tr><td>李四</td><td><span>女</span></td><td>22</td></tr>
        <tr><td>王五</td><td>男</td><td>23</td></tr>
        <tr><td>赵六</td><td><span>女</span></td><td>24</td></tr>
    </table>
    

    $('td:has(span)').css('background', 'red');
    

![image-20201111120813884](https://img-blog.csdnimg.cn/img_convert/5bb151fc8c2f131c60e3c2e4a99f4f62.png)

**需求描述：实现让内容为空的单元格的背景变为红色**

    <table cellspacing="0px" cellpadding="10px" border="1px">
        <tr><td>张三</td><td>男</td><td>21</td></tr>
        <tr><td>李四</td><td></td><td>22</td></tr>
        <tr><td>王五</td><td>男</td><td>23</td></tr>
        <tr><td>赵六</td><td></td><td>24</td></tr>
    </table>
    

    $('td:empty').css('background', 'red');
    

![image-20201111120205737](https://img-blog.csdnimg.cn/img_convert/786a5a015e7f2ca1351a0bdff359eb4d.png)

**需求描述：实现让内容不为空的单元格的背景变为红色**

    <table cellspacing="0px" cellpadding="10px" border="1px">
        <tr><td>张三</td><td>男</td><td>21</td></tr>
        <tr><td>李四</td><td></td><td>22</td></tr>
        <tr><td>王五</td><td>男</td><td>23</td></tr>
        <tr><td>赵六</td><td></td><td>24</td></tr>
    </table>
    

    $('td:parent').css('background', 'red');
    

![image-20201111120622665](https://img-blog.csdnimg.cn/img_convert/9ca0984f50af048d75282e64be75da6e.png)

##### 2.1.3.3、属性筛选器

**需求描述：查找herflang属性的标签元素，设置其背景为红色**

    <a href="" hreflang="en">en</a>
    <a href="" hreflang="en-UK">en-UK</a>
    <a href="" hreflang="zh-CN">zh-CN</a>
    

    $('[hreflang]').css('background', 'red');
    

![image-20201112091316884](https://img-blog.csdnimg.cn/img_convert/d1c6965fa9aca1b60672e56854496a91.png)

**需求描述：查找hreflang属性值是en的所有超链接，设置其背景为红色**

    <a href="" hreflang="en">en</a>
    <a href="" hreflang="en-UK">en-UK</a>
    <a href="" hreflang="zh-CN">zh-CN</a>
    

    $('a[hreflang="en"]').css('background', 'red');
    

![image-20201112091734984](https://img-blog.csdnimg.cn/img_convert/8c5333b62f5591df6c7665b154bb3f73.png)

**需求描述：查找hreflang属性值不是en的所有超链接，设置其背景为红色**

    <a href="" hreflang="en">en</a>
    <a href="" hreflang="en-UK">en-UK</a>
    <a href="" hreflang="zh-CN">zh-CN</a>
    

    $('a[hreflang!="en"]').css('background', 'red');
    

![image-20201112091926200](https://img-blog.csdnimg.cn/img_convert/a52c46fdbef5342bf4b18a00a0a64ab2.png)

**需求描述：查找hreflang属性值是en或者以en开头的所有超链接，设置其背景为红色**

    <a href="" hreflang="en">en</a>
    <a href="" hreflang="en-UK">en-UK</a>
    <a href="" hreflang="zh-CN">zh-CN</a>
    

    $('a[hreflang|="en"]').css('background', 'red');
    或者
    $('a[hreflang^="en"]').css('background', 'red');
    

![image-20201112091126256](https://img-blog.csdnimg.cn/img_convert/48de526adc7926a054051f94e84500a1.png)

**需求描述：查找hreflang属性值是以给定值CN结尾的元素，设置其背景为红色**

    <a href="" hreflang="en">en</a>
    <a href="" hreflang="en-UK">en-UK</a>
    <a href="" hreflang="zh-CN">zh-CN</a>
    

    $('a[hreflang$="CN"]').css('background', 'red');
    

![image-20201112093211690](https://img-blog.csdnimg.cn/img_convert/779e004962151f89f96f726c4fd2aba7.png)

**需求描述：选择hreflang属性具有包含一个给定的子字符串CN的超链接，设置其背景为红色**

    <a href="" hreflang="en">en</a>
    <a href="" hreflang="en-UK">en-UK</a>
    <a href="" hreflang="zh-CN">zh-CN</a>
    

    $('a[hreflang*="CN"]').css('background', 'red');
    

![image-20201112092429193](https://img-blog.csdnimg.cn/img_convert/eaa76ec012da967e392a9aee1de49ba0.png)

**需求描述：选择hreflang属性用空格分隔的值中包含一个给定值为CN的超链接，设置其背景为红色**

    <a href="" hreflang="en">en</a>
    <a href="" hreflang="en UK">en-UK</a>
    <a href="" hreflang="zh CN">zh-CN</a>
    

    $('a[hreflang~="CN"]').css('background', 'red');
    

![image-20201112092856115](https://img-blog.csdnimg.cn/img_convert/fa6667304a707c64e9d0caa9be501a5e.png)

**需求描述：选择hreflang属性为zh-CN，title属性为Chinese的超链接，设置其背景为红色**

    <a href="" hreflang="en">en</a>
    <a href="" hreflang="en-UK">en-UK</a>
    <a href="" hreflang="zh-CN" title="Chinese">zh-CN</a>
    

    $('a[hreflang="zh-CN"][title="Chinese"]').css('background', 'red');
    

![image-20201112095539910](https://img-blog.csdnimg.cn/img_convert/81c6761453f8d7d410d2a0cfab93d971.png)

##### 2.1.3.4、可见性筛选器

**需求描述：让隐藏的段落显示出来**

    <p style="display: block">我是显示段落</p>
    <p style="display: none">我是隐藏段落</p>
    

    $('p:hidden').css('display', 'block');
    

![image-20201112100048861](https://img-blog.csdnimg.cn/img_convert/110cbac5450ea3a52d4e2d59f25fe1ac.png)

**需求描述：让显示的段落隐藏起来**

    <p style="display: block">我是显示段落</p>
    <p style="display: none">我是隐藏段落</p>
    

    $('p:visible').css('display', 'none');
    

![image-20201112100256467](https://img-blog.csdnimg.cn/img_convert/7860a130603979d59b39db13c66c28e7.png)

##### 2.1.3.5、子元素筛选器

**需求描述：选择所有父级元素ul下的第一个子元素li，设置其背景为红色**

    <ul>
        <li>我是列表项1</li>
        <li>我是列表项2</li>
        <li>我是列表项3</li>
        <li>我是列表项4</li>
    </ul>
    

    $('ul li:first-child').css('background', 'red');
    

![image-20201112101446747](https://img-blog.csdnimg.cn/img_convert/9f8f76c500c7b0524b4c0c07278d5d46.png)

**需求描述：选择所有父级元素ul下的最后一个子元素li，设置其背景为红色**

    <ul>
        <li>我是列表项1</li>
        <li>我是列表项2</li>
        <li>我是列表项3</li>
        <li>我是列表项4</li>
    </ul>
    

    $('ul li:last-child').css('background', 'red');
    

![image-20201112101837483](https://img-blog.csdnimg.cn/img_convert/e4ac16607f435e7a951bc2afd43d3a8c.png)

**需求描述：选择所有父级元素ul下的第二个子元素li，设置其背景为红色**

    <ul>
        <li>我是列表项1</li>
        <li>我是列表项2</li>
        <li>我是列表项3</li>
        <li>我是列表项4</li>
    </ul>
    

    $('ul li:nth-child(2)').css('background', 'red');
    

![image-20201112104323763](https://img-blog.csdnimg.cn/img_convert/140459d73e7988346d036440bbe13057.png)

#### 2.1.4、表单选择器

##### 2.1.4.1、表单类型选择器

**需求描述：选中表单中的文本框、密码框、文件框、按钮、提交按钮、重置按钮等，设置其背景为红色**

    <form>
        <input type="text"><br>
        <input type="password"><br>
        <input type="file"><br>
        <input type="button" value="按钮"><br>
        <input type="submit" value="提交按钮"><br>
        <input type="reset" value="重置按钮"><br>
    </form>
    

    $('input:text').css('background', 'red');
    $('input:password').css('background', 'red');
    $('input:file').css('background', 'red');
    $('input:button').css('background', 'red');
    $('input:submit').css('background', 'red');
    $('input:reset').css('background', 'red');
    

![image-20201112105954052](https://img-blog.csdnimg.cn/img_convert/0e4d053de0390ffc9802f72a8b678660.png)

**需求描述：选中复选框、单选框，然后输出标签信息**

    <form>
        <input type="checkbox">复选框<br>
        <input type="radio">单选框<br>
    </form>
    

    console.log($(':checkbox')[0]);
    console.log($(':radio')[0]);
    

![image-20201112111743216](https://img-blog.csdnimg.cn/img_convert/adc77f45a347596b7f397b401b73ad50.png)

##### 2.1.4.2、表单状态选择器

**需求描述：输出表单获取焦点、表单选中、表单禁用、表单列表项选中的状态所在的标签信息**

    <form>
        <input type="text" autofocus><br>
        <input type="checkbox" checked>复选框<br>
        <input type="radio" disabled>单选框<br>
        <select>
            <option selected>列表项1</option>
            <option>列表项2</option>
        </select>
    </form>
    

    console.log($(':focus')[0]);
    console.log($(':checked')[0]);
    console.log($(':disabled')[0]);
    console.log($(':selected')[0]);
    

![image-20201112111607308](https://img-blog.csdnimg.cn/img_convert/58622e8a6ceaaa92ce138aa80d732575.png)

### 2.2、工具

#### 2.2.1、$.each方法

方法描述：一个通用的迭代函数，它可以用来无缝迭代对象和数组。数组和类似数组的对象通过一个长度属性（如一个函数的参数对象）来迭代数字索引，从0到length - 1，其他对象通过其属性名进行迭代。

**需求描述：给定一个数组，使用$.each方法进行遍历输出**

    var arr = [10, 90, 20, 80, 30, 70, 40, 60, 50];
    $.each(arr, function (index, element) {
        console.log(index, element);
    });
    

![image-20201112150402126](https://img-blog.csdnimg.cn/img_convert/b9a40d8ae7f030960732189f021bbd0a.png)

**需求描述：给定一个对象，使用$.each方法进行遍历输出**

    var obj = {
        name: 'Tom',
        age: 28,
        speak: function () {}
    };
    $.each(obj, function (key, value) {
        console.log(key, value);
    });
    

![image-20201112150826663](https://img-blog.csdnimg.cn/img_convert/af1cdea6f5f89ee9ed4243db67209563.png)

#### 2.2.2、$.trim方法

方法描述：去掉字符串起始和结尾的空格。

**需求描述：给定一个字符串，去掉该字符串的前后空格**

    var str = '    hello    ';
    console.log($.trim(str));
    

![image-20201112153235248](https://img-blog.csdnimg.cn/img_convert/dcd76e2d835641f360490766468503bf.png)

#### 2.2.3、$.type方法

方法描述：确定JavaScript 对象的类型。

**需求描述：给定一个对象，输出该对象的类型**

    var str = '    hello    ';
    console.log($.type(str));
    

![image-20201112153751009](https://img-blog.csdnimg.cn/img_convert/81ee4428b320e6fe0ae0679ede29dfd2.png)

#### 2.2.4、$.isArray方法

方法描述：用来测试指定对象是否为一个数组。

**需求描述：给定一个对象，输出该对象是不是数组类型**

    var arr = [10, 90, 20, 80, 30, 70, 40, 60, 50];
    console.log($.isArray(arr));
    

![image-20201112154343259](https://img-blog.csdnimg.cn/img_convert/082723598a94ad5838cdf1d910c16942.png)

#### 2.2.5、$.isFunction方法

方法描述：用来测试指定对象是否为一个函数。

**需求描述：给定一个对象，输出该对象是不是函数类型**

    var fun = function () {
        console.log("hello");
    };
    console.log($.isFunction(fun));
    

![image-20201112154758585](https://img-blog.csdnimg.cn/img_convert/c13efb1256cde64dc2af69390a0d24a7.png)

### 2.3、ajax

#### 2.3.1、$.ajax方法

方法描述：执行一个异步的HTTP的请求。

**需求描述：执行一个异步的HTTP GET请求，从服务器加载数据。**

    $.ajax({
        url: '/user/login',
        type: 'get',
        data: {
            username: 'zhangsan',
            password: '123456'
        },
        dataType: 'text',
        success: function (response) {
            alert(response);
        },
        error: function (response) {
            alert(response);
        }
    });
    

**需求描述：执行一个异步的HTTP POST请求，从服务器加载数据。**

    $.ajax({
        url: '/user/login',
        type: 'post',
        data: {
            username: 'zhangsan',
            password: '123456'
        },
        dataType: 'text',
        success: function (response) {
            alert(response);
        },
        error: function (response) {
            alert(response);
        }
    });
    

#### 2.3.2、$.get方法

方法描述：使用一个HTTP GET请求从服务器加载数据。

这是一个ajax功能的缩写，这相当于:

    $.ajax({
        url: url,
        data: data,
        success: success,
        dataType: dataType
    });
    

    $.get('/user/login', {username: 'zhangsan', password: '123456'}, function (response) {
        alert(response);
    });
    

#### 2.3.3、$.post方法

方法描述：使用一个HTTP POST请求从服务器加载数据。

这是一个ajax功能的缩写，这相当于:

    $.ajax({
        url: url,
        data: data,
        success: success,
        dataType: dataType
    });
    

    $.post('/user/login', {username: 'zhangsan', password: '123456'}, function (response) {
        alert(response);
    });
    

第三章 jQuery核心对象
--------------

### 3.1、属性

#### 3.1.1、属性

##### 3.1.1.1、attr()

方法描述：专门操作属性值为非布尔值的属性，该方法读写一体。

**需求描述：设置p标签的title属性为”我是attr修改后的段落标题“**

    <p id="content" title="我是段落标题">我是段落</p>
    

    $('#content').attr('title', '我是attr修改后的段落标题');
    

![image-20201112173818651](https://img-blog.csdnimg.cn/img_convert/f0ce790ee4d80a45402aff2cfde47616.png)

**需求描述：读取p标签的title属性并输出**

    <p id="content" title="我是段落标题">我是段落</p>
    

    console.log($('#content').attr('title'));
    

![image-20201112173942146](https://img-blog.csdnimg.cn/img_convert/a11816a3d35a5790e89e84b699fd6089.png)

##### 3.1.1.2、prop()

方法描述：专门操作属性值为布尔值的属性，该方法读写一体。

**需求描述：设置复选框的状态为选中状态**

    <input type="checkbox">复选框
    

    $(':checkbox').prop('checked', 'true');
    

![image-20201112174254845](https://img-blog.csdnimg.cn/img_convert/8e5b05d84366ba904f0c389c2ba4245b.png)

**需求描述：读取复选框的选中状态并输出**

    <input type="checkbox" checked>复选框
    

    console.log($(':checkbox').prop('checked'));
    

![image-20201112174448411](https://img-blog.csdnimg.cn/img_convert/47dc1d85c48210cd90d2e9995527d193.png)

##### 3.1.1.3、val()

方法描述：该方法主要用于获取表单元素的值和设置表单元素的值，该方法读写一体。

**需求描述：设置文本框的值为”123456“**

    <input type="text">
    

    $(':text').val('123456');
    

![image-20201112174730206](https://img-blog.csdnimg.cn/img_convert/289b95660891221fb0a39566a849e6d9.png)

**需求描述：读取文本框的值并输出**

    <input type="text" value="123456">
    

    console.log($(':text').val());
    

![image-20201112175045084](https://img-blog.csdnimg.cn/img_convert/da0180d1fa502696978b34d65914f000.png)

#### 3.1.2、样式

##### 3.1.2.1、css()

方法描述：获取匹配元素集合中的第一个元素的样式属性的计算值或设置每个匹配元素的一个或多个CSS属性。

**需求描述：设置div的背景颜色为红色，字体颜色为白色**

    <div>我是div</div>
    

    $('div').css({
        'background': 'red',
        'color': 'white'
    });
    

![image-20201112210702861](https://img-blog.csdnimg.cn/img_convert/1adaa3a3aaa0da9cdcf9565539c256e6.png)

**需求描述：获取div的背景颜色和字体颜色并输出**

    <div style="background: red;color: white">我是div</div>
    

    console.log($('div').css('background'));
    console.log($('div').css('color'));
    

![image-20201112210937731](https://img-blog.csdnimg.cn/img_convert/0d7221e791f6fc50d9638dece33a3a27.png)

##### 3.1.2.2、addClass()

方法描述：为每个匹配的元素添加指定的样式类名。

**需求描述：为所有的li添加样式”beauty“**

    .beauty {
        font-weight: bold;
        font-size: 18px;
        color: coral;
    }
    

    <ul>
        <li>列表项1</li>
        <li>列表项2</li>
        <li>列表项3</li>
        <li>列表项4</li>
    </ul>
    

    $('li').addClass('beauty');
    

![image-20201112211305303](https://img-blog.csdnimg.cn/img_convert/d448b3e4c4279dfd1c82c4e1d24755a3.png)

##### 3.1.2.3、removeClass()

方法描述：移除集合中每个匹配元素上一个，多个或全部样式。

**需求描述：为所有的li移除样式”beauty“**

    .beauty {
        font-weight: bold;
        font-size: 18px;
        color: coral;
    }
    

    <ul>
        <li class="beauty">列表项1</li>
        <li class="beauty">列表项2</li>
        <li class="beauty">列表项3</li>
        <li class="beauty">列表项4</li>
    </ul>
    

    $('li').removeClass('beauty');
    

![image-20201112211549376](https://img-blog.csdnimg.cn/img_convert/2f1004c81c87e16a67038bcb9d06f26b.png)

##### 3.1.2.4、hasClass()

方法描述：确定任何一个匹配元素是否有被分配给定的样式类。

**需求描述：判断p标签是否包含”beauty“的样式**

    .beauty {
        font-weight: bold;
        font-size: 18px;
        color: coral;
    }
    

    <p class="beauty"></p>
    

    console.log($('p').hasClass('beauty'));
    

![image-20201112212506796](https://img-blog.csdnimg.cn/img_convert/df54a0d34c93ca1b1797051f9a77f6cb.png)

##### 3.1.2.5、toggleClass()

方法描述：为匹配的元素集合中的每个元素上添加或删除一个或多个样式类，取决于这个样式类是否存在。

> 注意：如果存在（不存在）就删除（添加）一个样式类

**需求描述：当单击按钮的时候，隐藏div，再次单击按钮的时候，显示div**

    .hide {
        width: 100px;
        height: 100px;
        display: none;
    }
    

    <button>按钮</button>
    <div>我是div</div>
    

    $('button').click(function () {
        $('div').toggleClass('hide');
    });
    

![1](https://img-blog.csdnimg.cn/img_convert/6120c0c7162046b970e5fc4190065400.gif)

#### 3.1.3、尺寸

##### 3.1.3.1、width()

方法描述：获取内容元素width的值。

##### 3.1.3.2、height()

方法描述：获取内容元素height的值。

##### 3.1.3.3、innerWidth()

方法描述：获取内容元素width+padding的值。

##### 3.1.3.4、innerHeight()

方法描述：获取内容元素height+padding的值。

##### 3.1.3.5、outerWidth()

方法描述：outerWidth(false/true)，获取内容元素width+padding+border的值，如果是true再加上margin的值。

##### 3.1.3.6、outerHeight()

方法描述：outerHeight(false/true)，获取内容元素height+padding+border的值，如果是true再加上margin的值。

##### 3.1.3.7、综合演示

**需求描述：创建按一个div，获取以上六种值**

    .box {
        margin: 30px;
        padding: 20px;
        border: 10px;
        width: 100px;
        height: 100px;
        background: coral;
    }
    

    <div class="box"></div>
    

    var $box = $('.box');
    console.log($box.width(), $box.height());// 100 100
    console.log($box.innerWidth(), $box.innerHeight());// 140 140
    console.log($box.outerWidth(), $box.outerHeight());// 160 160
    console.log($box.outerWidth(true), $box.outerHeight(true));// 220 220
    

#### 3.1.4、位置

##### 3.1.4.1、offset()

方法描述：相对页面左上角的坐标。

**需求描述：获取div相对页面左上角的坐标**

    .box {
        width: 100px;
        height: 100px;
        background: coral;
    }
    

    <div class="box"></div>
    

    var offset = $('.box').offset();
    console.log(offset.left, offset.top);
    

![image-20201113081934904](https://img-blog.csdnimg.cn/img_convert/7cfecd45d65a88e9afcc704e0ff6fde0.png)

##### 3.1.4.2、position()

方法描述：相对于父元素左上角的坐标。

**需求描述：获取div相对于父元素左上角的坐标**

    .box-container {
        width: 300px;
        height: 300px;
        background: pink;
        position: absolute;
        left: 20px;
        top: 20px;
    }
    
    .box {
        width: 100px;
        height: 100px;
        background: coral;
        position: absolute;
        left: 20px;
        top: 20px;
    }
    

    <div class="box-container">
        <div class="box"></div>
    </div>
    

    var offset = $('.box').position();
    console.log(offset.left, offset.top);
    

![image-20201113082307166](https://img-blog.csdnimg.cn/img_convert/d1dbb603b197dd5adce9ee366df26c6a.png)

##### 3.1.4.3、scrollLeft()

方法描述：读取/设置滚动条的X坐标，该方法读写合一。

读取页面滚动条的Y坐标(兼容chrome和IE)

    var scrollLeft = $(document.body).scrollLeft()+$(document.documentElement).scrollLeft();
    

设置页面滚动条滚动到指定位置(兼容chrome和IE)

    $('body,html').scrollLeft(60);
    

**需求描述：设置页面的宽度为2000px，设置滚动条的X轴坐标为300px，要求兼容各种浏览器**

    $('body').css('width', '2000px');
    $('html,body').scrollLeft(300);
    

##### 3.1.4.4、scrollTop()

方法描述：读取/设置滚动条的Y坐标，该方法读写合一。

读取页面滚动条的Y坐标(兼容chrome和IE)

    var scrollTop = $(document.body).scrollTop()+$(document.documentElement).scrollTop();
    

设置页面滚动条滚动到指定位置(兼容chrome和IE)

    $('body,html').scrollTop(60);
    

**需求描述：设置页面的高度为2000px，设置滚动条的Y轴坐标为300px，要求兼容各种浏览器**

    $('body').css('height', '2000px');
    $('html,body').scrollTop(300);
    

### 3.2、操作

#### 3.2.1、DOM内部插入

##### 3.2.1.1、text()

方法描述：设置/获取元素的文本内容，该方法读写合一。

**需求描述：设置p段落标签的内容为“我是段落”**

    <p></p>
    

    $('p').text('我是段落');
    

![image-20201113095528518](https://img-blog.csdnimg.cn/img_convert/e51da6dfecaed0059140eeaa59ff393a.png)

**需求描述：获取p段落标签的内容并输出**

    <p>我是段落</p>
    

    console.log($('p').text());
    

![image-20201113095705829](https://img-blog.csdnimg.cn/img_convert/9abfe466f3720c923e19d684b406c3c2.png)

##### 3.2.1.2、html()

方法描述：设置/获取元素的html内容，该方法读写合一。

**需求描述：设置ul列表标签的li列表项**

    <ul></ul>
    

    var li = '<li>我是列表项</li>';
    $('ul').html(li);
    

![image-20201113095925458](https://img-blog.csdnimg.cn/img_convert/cef763ccbaa61e2b1acb21e4ee5eb8cf.png)

**需求描述：获取ul列表中的列表项并输出**

    <ul><li>我是列表项</li></ul>
    

    console.log($('ul').html());
    

![image-20201113100057187](https://img-blog.csdnimg.cn/img_convert/ae7c40da63b815e277a9a566a75afb76.png)

##### 3.2.1.3、append()

方法描述：向当前匹配的所有元素内部的最后面插入指定内容。

**需求描述：为当前的ul向后添加一个列表项**

    <ul>
        <li>我是列表项1</li>
        <li>我是列表项2</li>
    </ul>
    

    var last = '<li>我是最后一个列表项</li>';
    $('ul').append(last);
    

![image-20201113100558048](https://img-blog.csdnimg.cn/img_convert/30f20facb9f262c80ed3cf0b243ab7ad.png)

##### 3.2.1.4、appendTo()

方法描述：将指定的内容追加到当前匹配的所有元素的最后面。

**需求描述：为当前的ul向后添加一个列表项**

    <ul>
        <li>我是列表项1</li>
        <li>我是列表项2</li>
    </ul>
    

    var last = '<li>我是最后一个列表项</li>';
    $(last).appendTo($('ul'));
    

![image-20201113100558048](https://img-blog.csdnimg.cn/img_convert/5ea7b5f900b5e10e323284ea26f25af7.png)

##### 3.2.1.5、prepend()

方法描述：向当前匹配的所有元素内部的最前面插入指定内容。

**需求描述：为当前的ul向前添加一个列表项**

    <ul>
        <li>我是列表项1</li>
        <li>我是列表项2</li>
    </ul>
    

    var first = '<li>我是第一个列表项</li>';
    $('ul').prepend(first);
    

![image-20201113100940938](https://img-blog.csdnimg.cn/img_convert/2a56530ca28fbd6538f9cbc814fc02b2.png)

##### 3.2.1.6、prependTo()

方法描述：将指定的内容追加到当前匹配的所有元素的最前面。

**需求描述：为当前的ul向前添加一个列表项**

    <ul>
        <li>我是列表项1</li>
        <li>我是列表项2</li>
    </ul>
    

    var first = '<li>我是第一个列表项</li>';
    $(first).prependTo($('ul'));
    

![image-20201113100940938](https://img-blog.csdnimg.cn/img_convert/09accb3504b17b5f7ce2ac9aa012b231.png)

#### 3.2.2、DOM外部插入

##### 3.2.2.1、after()

方法描述：在匹配元素集合中的每个元素后面插入参数所指定的内容，作为其兄弟节点。

**需求描述：在div的后边插入一个段落**

    <div>我是div</div>
    

    var after = '<p>我是段落</p>';
    $('div').after(after);
    

![image-20201113101726137](https://img-blog.csdnimg.cn/img_convert/cfc5e9b8db6871e46c062af5ad99c7f7.png)

##### 3.2.2.2、before()

方法描述：在匹配元素集合中的每个元素前边插入参数所指定的内容，作为其兄弟节点。

**需求描述：在div的前边插入一个段落**

    <div>我是div</div>
    

    var before = '<p>我是段落</p>';
    $('div').before(before);
    

![image-20201113101831389](https://img-blog.csdnimg.cn/img_convert/58dabcc83d368ba8ee7767bca030ed54.png)

##### 3.2.2.3、insertAfter()

方法描述：.after()和.insertAfter() 实现同样的功能。主要的不同是语法，特别是插入内容和目标的位置。 对于 .after()，选择表达式在函数的前面，参数是将要插入的内容。对于 .insertAfter()，刚好相反，内容在方法前面，它将被放在参数里元素的后面。

**需求描述：在div的后边插入一个段落**

    <div>我是div</div>
    

    var content = '<p>我是段落</p>';
    $(content).insertAfter($('div'));
    

![image-20201113101726137](https://img-blog.csdnimg.cn/img_convert/cfc5e9b8db6871e46c062af5ad99c7f7.png)

##### 3.2.2.4、insertBefore()

方法描述：.before()和.insertBefore()实现同样的功能。主要的不同是语法，特别是插入内容和目标的位置。 对于 .before()，选择表达式在函数前面，参数是将要插入的内容。对于 .insertBefore()，刚好相反，内容在方法前面，它将被放在参数里元素的前面。

**需求描述：在div的前边插入一个段落**

    <div>我是div</div>
    

    var content = '<p>我是段落</p>';
    $(content).insertBefore($('div'));
    

![image-20201113101831389](https://img-blog.csdnimg.cn/img_convert/58dabcc83d368ba8ee7767bca030ed54.png)

#### 3.2.3、DOM移除

##### 3.2.3.1、empty()

方法描述：删除所有匹配元素的子元素。

**需求描述：将ul列表下所有的子节点全部移除**

    <ul>
        <li>列表项1</li>
        <p>我是段落1</p>
        <li>列表项2</li>
        <p>我是段落2</p>
        <li>列表项3</li>
    </ul>
    

    $('ul').empty();
    

![image-20201113134718228](https://img-blog.csdnimg.cn/img_convert/926785f63fcc1396a97278e796cb5200.png)

##### 3.2.3.2、remove()

方法描述：删除所有匹配的元素。

> 注意：同时移除元素上的事件及 jQuery 数据

**需求描述：将ul列表下所有的p子节点全部移除**

    <ul>
        <li>列表项1</li>
        <p>我是段落1</p>
        <li>列表项2</li>
        <p>我是段落2</p>
        <li>列表项3</li>
    </ul>
    

    $('ul>p').remove();
    

![image-20201113135157720](https://img-blog.csdnimg.cn/img_convert/c9e3ec18fe3c3c36b56d7522f51f6bc9.png)

#### 3.2.4、DOM替换

##### 3.2.4.1、replaceWith()

方法介绍：用提供的内容替换集合中所有匹配的元素并且返回被删除元素的集合。

**需求描述：将ul下的所有li替换为p标签**

    <ul>
        <li>列表项1</li>
        <li>列表项2</li>
        <li>列表项3</li>
    </ul>
    

    $('ul>li').replaceWith('<p>我是段落</p>');
    

![image-20201113141113105](https://img-blog.csdnimg.cn/img_convert/6b8bdb239a381b05199d4e47ef16a4b0.png)

##### 3.2.4.2、replaceAll()

方法介绍：`.replaceAll()`和`.replaceWith()`功能类似，但是目标和源相反。

**需求描述：将ul下的所有li替换为p标签**

    <ul>
        <li>列表项1</li>
        <li>列表项2</li>
        <li>列表项3</li>
    </ul>
    

    $('<p>我是段落</p>').replaceAll($('ul>li'));
    

![image-20201113141113105](https://img-blog.csdnimg.cn/img_convert/364226893eacb1fea5258d5a22bdcb80.png)

#### 3.2.5、DOM拷贝

##### 3.2.5.1、clone()

方法描述：创建一个匹配的元素集合的深度拷贝副本。如果传入一个true，则表示是否会复制元素上的事件处理函数，从jQuery 1.4开始，元素数据也会被复制。

**需求描述：为ul列表创建一个深克隆并追加到body后**

    <ul>
        <li>列表项1</li>
        <li>列表项2</li>
        <li>列表项3</li>
    </ul>
    

    var ul = $('#ul').clone();
    $('body').append(ul);
    

![image-20201113142643169](https://img-blog.csdnimg.cn/img_convert/ac8a3eccf2fca161ddae9723cc024bb5.png)

#### 3.2.6、DOM遍历

##### 3.2.6.1、parent()

方法描述：获取集合中每个匹配元素的父元素，可以提供一个可选的选择器来进行筛选。

**需求描述：输出id为two的li的父元素**

    <ul>
        <p>我是段落1</p>
        <li>列表项1</li>
        <li id="two">列表项2</li>
        <li>列表项3</li>
        <p>我是段落2</p>
    </ul>
    

    console.log($('#two').parent()[0]);
    

![image-20201113160103802](https://img-blog.csdnimg.cn/img_convert/69f9eccd3a55d2141744ac424080b7c3.png)

##### 3.2.6.2、children()

方法描述：获取集合中每个匹配元素的子元素，可以提供一个可选的选择器来进行筛选。

**需求描述：输出ul下的所有子元素**

    <ul>
        <p>我是段落1</p>
        <li>列表项1</li>
        <li id="two">列表项2</li>
        <li>列表项3</li>
        <p>我是段落2</p>
    </ul>
    

    var childrens = $('ul').children();
    for (var i = 0; i < childrens.length; i++) {
        console.log(childrens[i]);
    }
    

![](https://img-blog.csdnimg.cn/img_convert/2e0e5a9d57ba3e1075804a0b20feb7a4.png)

##### 3.2.6.3、prev()

方法描述：获取集合中每个匹配元素紧邻的前一个兄弟元素，可以提供一个可选的选择器来进行筛选。

**需求描述：获取id为two元素的前一个兄弟元素并输出**

    <ul>
        <p>我是段落1</p>
        <li>列表项1</li>
        <li id="two">列表项2</li>
        <li>列表项3</li>
        <p>我是段落2</p>
    </ul>
    

    console.log($('#two').prev()[0]);
    

![image-20201113160609018](https://img-blog.csdnimg.cn/img_convert/138c92af8472d12fbfe1445c21b49632.png)

##### 3.2.6.4、prevAll()

方法描述：获得集合中每个匹配元素的所有前面的兄弟元素，可以提供一个可选的选择器来进行筛选。

**需求描述：获取id为two元素的前边所有的兄弟元素并输出**

    <ul>
        <p>我是段落1</p>
        <li>列表项1</li>
        <li id="two">列表项2</li>
        <li>列表项3</li>
        <p>我是段落2</p>
    </ul>
    

    var prevs = $('#two').prevAll();
    for (var i = 0; i < prevs.length; i++) {
        console.log(prevs[i]);
    }
    

![image-20201113160818258](https://img-blog.csdnimg.cn/img_convert/075248d4241092e4880fccb9f4377dd2.png)

##### 3.2.6.5、next()

方法描述：获取集合中每个匹配元素紧邻的后一个兄弟元素，可以提供一个可选的选择器来进行筛选。

**需求描述：获取id为two元素的后一个兄弟元素并输出**

    <ul>
        <p>我是段落1</p>
        <li>列表项1</li>
        <li id="two">列表项2</li>
        <li>列表项3</li>
        <p>我是段落2</p>
    </ul>
    

    console.log($('#two').next()[0]);
    

![image-20201113160653695](https://img-blog.csdnimg.cn/img_convert/369beeec355bcf4daeb63d81b1e04f3f.png)

##### 3.2.6.6、nextAll()

方法描述：获得集合中每个匹配元素的所有后面的兄弟元素，可以提供一个可选的选择器来进行筛选。

**需求描述：获取id为two元素的后边所有的兄弟元素并输出**

    <ul>
        <p>我是段落1</p>
        <li>列表项1</li>
        <li id="two">列表项2</li>
        <li>列表项3</li>
        <p>我是段落2</p>
    </ul>
    

    var nexts = $('#two').nextAll();
    for (var i = 0; i < nexts.length; i++) {
        console.log(nexts[i]);
    }
    

![image-20201113160909669](https://img-blog.csdnimg.cn/img_convert/9907c7c6bc2fc627efdfbb8a5b7972ac.png)

##### 3.2.6.7、siblings()

方法描述：获得集合中每个匹配元素的兄弟元素，可以提供一个可选的选择器来进行筛选。

**需求描述：获取id为two元素的所有兄弟元素并输出**

    <ul>
        <p>我是段落1</p>
        <li>列表项1</li>
        <li id="two">列表项2</li>
        <li>列表项3</li>
        <p>我是段落2</p>
    </ul>
    

    var siblings = $('#two').siblings();
    for (var i = 0; i < siblings.length; i++) {
        console.log(siblings[i]);
    }
    

![image-20201113161035419](https://img-blog.csdnimg.cn/img_convert/95e3ef167feeb83ab5a5692d79abae17.png)

### 3.3、遍历

#### 3.3.1、遍历

##### 3.3.1.1、each()

方法描述：遍历一个jQuery对象，为每个匹配元素执行一个函数。

**需求描述：获取每一个li元素并把每一个li元素的标签及内容输出**

    <ul>
        <p>我是段落1</p>
        <li>列表项1</li>
        <li id="two">列表项2</li>
        <li>列表项3</li>
        <p>我是段落2</p>
    </ul>
    

    $('li').each(function (index, element) {
        console.log(index, element);
    });
    

![image-20201113161908056](https://img-blog.csdnimg.cn/img_convert/f374e99a5324696ab49e8438afff0a22.png)

#### 3.3.2、筛选

##### 3.3.2.1、first()

方法描述：获取匹配元素集合中第一个元素。

**需求描述：设置ul下第一个li的背景为红色**

    <ul>
        <li>列表项1</li>
        <li id="two">列表项2</li>
        <li>列表项3</li>
    </ul>
    

    $('ul>li').first().css('background', 'red');
    

![image-20201113162641338](https://img-blog.csdnimg.cn/img_convert/bb08ac997a465e142ef15ad8654d71d2.png)

##### 3.3.2.2、last()

方法描述：获取匹配元素集合中最后一个元素。

**需求描述：设置ul下最后一个li的背景为红色**

    <ul>
        <li>列表项1</li>
        <li id="two">列表项2</li>
        <li>列表项3</li>
    </ul>
    

    $('ul>li').last().css('background', 'red');
    

![image-20201113162614635](https://img-blog.csdnimg.cn/img_convert/13f1d164a5672a734c5f1451a4941901.png)

##### 3.3.2.3、eq()

方法描述：获取匹配元素集合中指定位置索引的一个元素。

> 注意：索引下标从0开始

**需求描述：设置ul下第二个li的背景为红色**

    <ul>
        <li>列表项1</li>
        <li id="two">列表项2</li>
        <li>列表项3</li>
    </ul>
    

    $('ul>li').eq(1).css('background', 'red');
    

![image-20201113162850361](https://img-blog.csdnimg.cn/img_convert/783bff906c24c7b4247f8aa205ecaa99.png)

##### 3.3.2.4、not()

方法描述：从匹配的元素集合中移除指定的元素。

**需求描述：设置ul下li标签的背景为红色，排除第二个li**

    <ul>
        <li>列表项1</li>
        <li id="two">列表项2</li>
        <li>列表项3</li>
    </ul>
    

    var two = $('ul>li').eq(1);
    $('ul>li').not(two).css('background', 'red');
    

![image-20201113164056611](https://img-blog.csdnimg.cn/img_convert/2564412235a93162d9ea6c52fbf6faa5.png)

##### 3.3.2.5、filter()

方法描述：筛选元素集合中匹配表达式或通过传递函数测试的元素集合。

![image-20201113164236008](https://img-blog.csdnimg.cn/img_convert/4dd75f1983bfe3f2b92aa5bd0c336b27.png)

**需求描述：查找所有id为two的li标签设置其背景为红色**

    <ul>
        <li>列表项1</li>
        <li id="two">列表项2</li>
        <li>列表项3</li>
    </ul>
    

    $('ul>li').filter('[id=two]').css('background', 'red');
    

![image-20201113164417479](https://img-blog.csdnimg.cn/img_convert/fec2ae1f8ba1aa995609f67c7a4ccc39.png)

### 3.4、事件

#### 3.4.1、浏览器事件

##### 3.4.1.1、resize()

方法描述：为 JavaScript 的 “resize” 事件绑定一个处理函数，或者触发元素上的该事件。

**需求描述：当浏览器窗口的尺寸改变时，控制台输出“浏览器尺寸改变了”**

    $(window).resize(function () {
        console.log('浏览器尺寸改变了');
    });
    

![image-20201113165513522](https://img-blog.csdnimg.cn/img_convert/4a7ec9cc6d255abee601811b3d7e4447.png)

##### 3.4.1.2、scroll()

方法描述：为 JavaScript 的 “scroll” 事件绑定一个处理函数，或者触发元素上的该事件。

**需求描述：当浏览器窗口的滚动条滚动时，控制台输出“浏览器滚动条改变了”**

    body {
        height: 2000px;
    }
    

    $(window).scroll(function () {
        console.log('浏览器滚动条改变了');
    });
    

![image-20201113165656598](https://img-blog.csdnimg.cn/img_convert/76105c81a6aa188af7cb81a18c87b6ec.png)

#### 3.4.2、事件绑定

##### 3.4.2.1、on()

方法描述：在选定的元素上绑定一个或多个事件处理函数。

**需求描述：为按钮添加单击事件，当按钮单击的时候，向控制台输出“按钮被单击了”**

    <button>按钮</button>
    

    $('button').on('click',function () {
        console.log('按钮被单击了');
    });
    

![image-20201113170843098](https://img-blog.csdnimg.cn/img_convert/f9f68b64b116d641d6c1773ced67221a.png)

##### 3.4.2.2、off()

方法描述： 移除一个事件处理函数。

**需求描述：为按钮添加单击事件，然后再解绑，这时候你在点击按钮看看是不是不会输出信息了**

    <button>按钮</button>
    

    $('button').on('click',function () {
        console.log('按钮被单击了');
    });
    
    $('button').off('click');
    

![image-20201113171052034](https://img-blog.csdnimg.cn/img_convert/591d33fcc798eaff217a4a47f017afe0.png)

#### 3.4.3、事件委托

##### 3.4.3.1、delegate()

方法描述：设置事件委托。

**需求描述：为ul下的所有li添加单击事件，要求将该单击事件委托给ul，当单击li时，所对应的li背景变为红色**

    <ul>
        <li>1111</li>
        <li>2222</li>
        <li>3333</li>
        <li>4444</li>
    </ul>
    

    $('ul').delegate('li', 'click', function () {
        this.style.background = 'red';
    });
    

![7](https://img-blog.csdnimg.cn/img_convert/f75f0e4bc4cb19c0a25166780330081e.gif)

##### 3.4.3.2、undelegate()

方法描述：移除事件委托。

**需求描述：要求移除上一节中设置的事件委托，然后在分别点击li进行验证是否移除事件委托**

    <ul>
        <li>1111</li>
        <li>2222</li>
        <li>3333</li>
        <li>4444</li>
    </ul>
    

    // 设置事件委托
    $('ul').delegate('li', 'click', function () {
        this.style.background = 'red';
    });
    
    // 移除事件委托
    $('ul').undelegate('click');
    

![8](https://img-blog.csdnimg.cn/img_convert/4d8e33d06c4afd79758694aea4aa1115.gif)

#### 3.4.4、事件对象

对象属性名称

对象属性描述

event.currentTarget

当前执行的DOM元素。

event.target

触发事件的DOM元素。

event.pageX

相对于页面的左上角。

event.pageY

相对于页面的顶部。

event.clientX

相对于视口的左上角。

event.clientY

相对于视口的顶部。

event.offsetX

相对于事件元素左上角。

event.offsetY

相对于事件元素顶部。

event.key

键盘的按键信息。

event.preventDefault()

阻止事件默认行为。

event.stopPropagation()

防止事件向外冒泡。

#### 3.4.5、表单事件

##### 3.4.5.1、focus()

方法描述：当获取焦点时触发所绑定的函数。

**需求描述：当文本框获取焦点时，设置其背景为红色**

    <input type="text">
    

    $(':text').focus(function () {
        $(this).css('background', 'red');
    });
    

![image-20201113172343263](https://img-blog.csdnimg.cn/img_convert/16c882ffa8142038a7b4c9311c751367.gif)

##### 3.4.5.2、blur()

方法描述：当失去焦点时触发所绑定的函数。

**需求描述：当文本框获取焦点时，设置其背景为红色，当文本框失去焦点时，设置其背景为绿色**

    <input type="text">
    

    $(':text').focus(function () {
        $(this).css('background', 'red');
    });
    $(':text').blur(function () {
        $(this).css('background', 'green');
    });
    

![2](https://img-blog.csdnimg.cn/img_convert/447a419acd086003b2a5dc9476791288.gif)

##### 3.4.5.3、change()

方法描述：当内容改变时触发所绑定的函数。

**需求描述：当文本框内容改变时，就向控制台输出当前文本框的内容**

    <input type="text">
    

    $(':text').change(function () {
        console.log($(this).val());
    });
    

![3](https://img-blog.csdnimg.cn/img_convert/353867836249606b8d57ee59ac14f89c.gif)

**需求描述：当选择框的内容改变时，就向控制台输出当前选中项的内容**

    <select>
        <option>河北</option>
        <option>河南</option>
        <option>上海</option>
        <option>北京</option>
        <option>广东</option>
    </select>
    

    $('select').change(function () {
        console.log($(this).val());
    });
    

![4](https://img-blog.csdnimg.cn/img_convert/3da8385825128e503c7f222657d02815.gif)

##### 3.4.5.4、select()

方法描述：当内容选择时触发所绑定的函数。

**需求描述：当文本框的内容被选择时，就向控制台输出当前文本框的内容**

    <input type="text" value="123456">
    

    $('input').select(function () {
        console.log($(this).val());
    });
    

![5](https://img-blog.csdnimg.cn/img_convert/197a89dadb82b29650f18639fee43123.gif)

##### 3.4.5.5、submit()

方法描述：当表单提交时触发所绑定的函数。

**需求描述：当表单提交的时候，弹出对话框“表单提交了”**

    <form action="#">
        <input type="submit">
    </form>
    

    $('form').submit(function () {
        alert('表单提交了');
    });
    

![6](https://img-blog.csdnimg.cn/img_convert/c9ba10202875cb1af788a15ee54b64ca.gif)

#### 3.4.6、鼠标事件

##### 3.4.6.1、click()

方法描述：当鼠标单击时调用所绑定的函数。

**需求描述：为按钮绑定一个单击函数，然后点击按钮，在控制台输出“按钮被单击了”**

    <button>按钮</button>
    

    $('button').click(function () {
        console.log('按钮被单击了');
    });
    

![10](https://img-blog.csdnimg.cn/img_convert/1da3010e4a222a6e94af538a208d5788.gif)

##### 3.4.6.2、dblclick()

方法描述：当鼠标双击时调用所绑定的函数。

**需求描述：为按钮绑定一个双击函数，然后双击按钮，在控制台输出“按钮被单击了”**

    <button>按钮</button>
    

    $('button').dblclick(function () {
        console.log('按钮被双击了');
    });
    

![11](https://img-blog.csdnimg.cn/img_convert/2f5e75556004f2b310b0919c13a78164.gif)

##### 3.4.6.3、mousedown()

方法描述：当鼠标左键按下的时候调用所绑定的函数。

**需求描述：当鼠标左键按下的时候，控制台输出“鼠标左键按下”**

    <button>按钮</button>
    

    $('button').mousedown(function () {
        console.log('鼠标左键按下');
    });
    

![12](https://img-blog.csdnimg.cn/img_convert/3ccced24dedfe20d0f6fbba4427e98e1.gif)

##### 3.4.6.4、mouseup()

方法描述：当鼠标左键松开的时候调用所绑定的函数。

**需求描述：当鼠标左键松开的时候，控制台输出“鼠标左键松开”**

    <button>按钮</button>
    

    $('button').mouseup(function () {
        console.log('鼠标左键松开');
    });
    

![13](https://img-blog.csdnimg.cn/img_convert/95ae4b07bd88116710a2852c7ab85570.gif)

##### 3.4.6.5、mouseenter()

方法描述：当鼠标进入目标元素的时候调用所绑定的函数。

**需求描述：创建两个div，当鼠标移到外层div的时候，向控制台输出“mouse enter”**

    .outer {
        width: 200px;
        height: 200px;
        background: coral;
    }
    
    .inner {
        width: 100px;
        height: 100px;
        background: pink;
    }
    

    <div class="outer">
        <div class="inner"></div>
    </div>
    

    $('.outer').mouseenter(function () {
        console.log('mouse enter');
    });
    

![14](https://img-blog.csdnimg.cn/img_convert/8e7240525833225f54076d9694fb68ef.gif)

##### 3.4.6.6、mouseleave()

方法描述：当鼠标离开目标元素的时候调用所绑定的函数。

**需求描述：创建两个div，当鼠标移出外层div的时候，向控制台输出“mouse leave”**

    .outer {
        width: 200px;
        height: 200px;
        background: coral;
    }
    
    .inner {
        width: 100px;
        height: 100px;
        background: pink;
    }
    

    <div class="outer">
        <div class="inner"></div>
    </div>
    

    $('.outer').mouseleave(function () {
        console.log('mouse leave');
    });
    

![15](https://img-blog.csdnimg.cn/img_convert/02c70090a84620135385f1cf993ab2e0.gif)

##### 3.4.6.7、mouseover()

方法描述：当鼠标进入目标元素的时候调用所绑定的函数。

> 注意：`mouseenter`事件和`mouseover`的不同之处是事件的冒泡的方式。`mouseenter` 事件只会在绑定它的元素上被调用，而不会在后代节点上被触发。

**需求描述：创建两个div，当鼠标移到外层div的时候，向控制台输出“mouse over”，鼠标移到内层div的时候，向控制台输出“mouse over”，当鼠标移到外层div的时候，向控制台输出“mouse over”**

    .outer {
        width: 200px;
        height: 200px;
        background: coral;
    }
    
    .inner {
        width: 100px;
        height: 100px;
        background: pink;
    }
    

    <div class="outer">
        <div class="inner"></div>
    </div>
    

    $('.outer').mouseover(function () {
        console.log('mouse over');
    });
    

![16](https://img-blog.csdnimg.cn/img_convert/28fad18bffa393b5aee7f84058e04d75.gif)

##### 3.4.6.8、mouseout()

方法描述：当鼠标离开目标元素的时候调用所绑定的函数。

> 注意：`mouseleave`事件和`mouseout`的不同之处是事件的冒泡的方式。`mouseleave` 事件只会在绑定它的元素上被调用，而不会在后代节点上被触发。

**需求描述：创建两个div，当鼠标移出外层div的时候，向控制台输出“mouse out”**

    .outer {
        width: 200px;
        height: 200px;
        background: coral;
    }
    
    .inner {
        width: 100px;
        height: 100px;
        background: pink;
    }
    

    <div class="outer">
        <div class="inner"></div>
    </div>
    

    $('.outer').mouseout(function () {
        console.log('mouse out');
    });
    

![17](https://img-blog.csdnimg.cn/img_convert/7802ad457d0256ad3c60811343ee1eac.gif)

##### 3.4.6.9、mousemove()

方法描述：当鼠标指针在元素内移动时，`mousemove`事件就会被触发，任何HTML元素都可以接受此事件。

**需求描述：鼠标在div内移动，获取当前鼠标相对div的位置坐标**

    .outer {
        width: 200px;
        height: 200px;
        background: black;
        position: absolute;
        left: 20px;
        top: 20px;
    }
    

    <div class="outer"></div>
    

    $('.outer').mousemove(function (event) {
        console.log(event.offsetX, event.offsetY);
    });
    

![19](https://img-blog.csdnimg.cn/img_convert/8ccc12034cd77aa642a6023c7bbcc4de.gif)

##### 3.4.6.10、hover()

方法描述：`.hover()`方法是同时绑定 `mouseenter`和 `mouseleave`事件。

**需求描述：当鼠标进入div设置背景为红色，当鼠标移出div设置背景为绿色，默认背景为黑色**

    .outer {
        width: 200px;
        height: 200px;
        background: black;
    }
    

    <div class="outer"></div>
    

    $('.outer').hover(function () {
        $(this).css('background', 'red');
    }, function () {
        $(this).css('background', 'green');
    });
    

![18](https://img-blog.csdnimg.cn/img_convert/5bd68756fcab6117f8f3c486db4ae22a.gif)

#### 3.4.7、键盘事件

##### 3.4.7.1、keydown()

方法描述：当键盘按键按下的时候调用绑定的函数。

**需求描述：当键盘按键按下的时候，输出当前的按键**

    <input type="text">
    

    $(':text').keydown(function (event) {
        console.log(event.key);
    });
    

![20](https://img-blog.csdnimg.cn/img_convert/f3bca9be80ac2edc7e270c12abfa7f69.gif)

##### 3.4.7.2、keyup()

方法描述：当键盘按键松开的时候调用绑定的函数。

**需求描述：当键盘按键松开的时候，输出当前的按键**

    <input type="text">
    

    $(':text').keyup(function (event) {
        console.log(event.key);
    });
    

![20](https://img-blog.csdnimg.cn/img_convert/f3bca9be80ac2edc7e270c12abfa7f69.gif)

##### 3.4.7.3、keypress()

方法描述：keypress与keydown类似，当键盘按键按下的时候调用绑定的函数。

**需求描述：当键盘按键按下的时候，输出当前的按键**

    <input type="text">
    

    $(':text').keypress(function (event) {
        console.log(event.key);
    });
    

![20](https://img-blog.csdnimg.cn/img_convert/f3bca9be80ac2edc7e270c12abfa7f69.gif)

### 3.5、动画

#### 3.5.1、基础

##### 3.5.1.1、hide()

方法描述：隐藏元素。

**需求描述：创建一个显示div，然后隐藏该元素**

    .box {
        width: 200px;
        height: 200px;
        background: coral;
        display: block;
    }
    

    <div class="box"></div>
    

    $('.box').hide();
    

![image-20201113210027194](https://img-blog.csdnimg.cn/img_convert/a1c228835186a8f4590960c9a9c1fcd8.png)

##### 3.5.1.2、show()

方法描述：显示元素。

**需求描述：创建一个隐藏div，然后显示该元素**

    .box {
        width: 200px;
        height: 200px;
        background: coral;
        display: none;
    }
    

    <div class="box"></div>
    

    $('.box').show();
    

![image-20201113210159713](https://img-blog.csdnimg.cn/img_convert/5e4412aadfe98953f4f2aec85b7fa4ed.png)

##### 3.5.1.3、toggle()

方法描述：如果隐藏就设置为显示，如果显示就设置为隐藏。

**需求描述：创建一个按钮，控制div显示和隐藏**

    .box {
        width: 200px;
        height: 200px;
        background: coral;
        display: block;
    }
    

    <button>隐藏/显示</button>
    <div class="box"></div>
    

    $('button').click(function () {
        $('.box').toggle();
    });
    

![21](https://img-blog.csdnimg.cn/img_convert/c3caeb30ff3006aa0ae80b4a9a4ee208.gif)

#### 3.5.2、渐变

##### 3.5.2.1、fadeIn()

方法描述：通过淡入的方式显示匹配元素。

**需求描述：创建一个按钮，控制div缓慢淡入**

    .box {
        width: 200px;
        height: 200px;
        background: coral;
        display: none;
    }
    

    <button>淡入</button>
    <div class="box"></div>
    

    $('button').click(function () {
        $('.box').fadeIn('slow');
    });
    

![22](https://img-blog.csdnimg.cn/img_convert/283d45d8eaddd2df86e593fb81807093.gif)

##### 3.5.2.2、fadeOut()

方法描述：通过淡出的方式隐藏匹配元素。

**需求描述：创建一个按钮，控制div缓慢淡出**

    .box {
        width: 200px;
        height: 200px;
        background: coral;
        display: block;
    }
    

    <button>淡出</button>
    <div class="box"></div>
    

    $('button').click(function () {
        $('.box').fadeOut('slow');
    });
    

![23](https://img-blog.csdnimg.cn/img_convert/fd6810f0e6631a083e46e28486a3a6c4.gif)

##### 3.5.2.3、fadeToggle()

方法描述：用淡入淡出动画显示或隐藏一个匹配元素。

**需求描述：创建一个按钮，控制div淡入和淡出**

    .box {
        width: 200px;
        height: 200px;
        background: coral;
        display: block;
    }
    

    <button>淡出/淡入</button>
    <div class="box"></div>
    

    $('button').click(function () {
        $('.box').fadeToggle('slow');
    });
    

![24](https://img-blog.csdnimg.cn/img_convert/0ad608fd44ec3b4d3d5e8ce058afec20.gif)

#### 3.5.3、滑动

##### 3.5.3.1、slideDown()

方法描述：用滑动动画显示一个匹配元素。

**需求描述：创建一个按钮，控制div滑动显示**

    .box {
        width: 200px;
        height: 200px;
        background: coral;
        display: none;
    }
    

    <button>滑动显示</button>
    <div class="box"></div>
    

    $('button').click(function () {
        $('.box').slideDown();
    });
    

![25](https://img-blog.csdnimg.cn/img_convert/f232a8161448c6b01692aafc89246751.gif)

##### 3.5.3.2、slideUp()

方法描述：用滑动动画隐藏一个匹配元素。

**需求描述：创建一个按钮，控制div滑动隐藏**

    .box {
        width: 200px;
        height: 200px;
        background: coral;
        display: block;
    }
    

    <button>滑动隐藏</button>
    <div class="box"></div>
    

    $('button').click(function () {
        $('.box').slideUp();
    });
    

![26](https://img-blog.csdnimg.cn/img_convert/dcc73f611c9954294080eced20bbf37d.gif)

##### 3.5.3.3、slideToggle()

方法描述：用滑动动画显示或隐藏一个匹配元素。

**需求描述：创建一个按钮，控制div滑动显示和滑动隐藏**

    .box {
        width: 200px;
        height: 200px;
        background: coral;
        display: block;
    }
    

    <button>滑动隐藏/滑动显示</button>
    <div class="box"></div>
    

    $('button').click(function () {
        $('.box').slideToggle();
    });
    

![27](https://img-blog.csdnimg.cn/img_convert/692c05fa49103f54e45c69cdaad6865c.gif)

#### 3.5.4、自定义

##### 3.5.4.1、animate()

方法描述：根据一组 CSS 属性，执行自定义动画，并且支持链式调用。

**需求描述：创建一个div，默认div宽高100px，背景颜色为黑色，先让div宽度变为200px，再让div高度变为200px**

    .box {
        width: 100px;
        height: 100px;
        background: black;
    }
    

    <button>自定义动画</button>
    <div class="box"></div>
    

    $('.box')
    .animate({
        width: '200'
    })
    .animate({
        height: '200',
    });
    

![28](https://img-blog.csdnimg.cn/img_convert/4ad491c049606496ad807835e4e926f1.gif)

##### 3.5.4.2、stop()

方法描述：停止匹配元素当前正在运行的动画。

第四章 jQuery插件介绍
--------------

### 4.1、扩展jQuery工具

给 **jQuery工具** 添加4个工具方法：

    min(a, b) : 返回较小的值
    max(c, d) : 返回较大的值
    leftTrim()  : 去掉字符串左边的空格
    rightTrim() : 去掉字符串右边的空格
    

如何实现呢？请参考以下代码：

    // 扩展jQuery工具的方法
    $.extend({
        min: function (a, b) {
            return a < b ? a : b
        },
        max: function (a, b) {
            return a > b ? a : b
        },
        leftTrim: function (str) {
            return str.replace(/^\s+/, '')
        },
        rightTrim: function (str) {
            return str.replace(/\s+$/, '')
        }
    });
    

    // 测试扩展jQuery工具的方法
    console.log($.min(3, 5));
    console.log($.max(3, 5));
    console.log('-----' + $.leftTrim('     hello     ') + '-----');
    console.log('-----' + $.rightTrim('     hello     ') + '-----');
    

![image-20201113214525050](https://img-blog.csdnimg.cn/img_convert/8619e8d0c012bf9322e2cb7799185d8e.png)

### 4.2、扩展jQuery对象

给 **jQuery对象** 添加3个功能方法：

    checkAll()     : 全选
    unCheckAll()   : 全不选
    reverseCheck() : 全反选
    

如何实现呢？请参考以下代码：

    // 扩展jQuery对象的方法
    $.fn.extend({
        checkAll: function () {
            this.prop('checked', true);
        },
        unCheckAll: function () {
            this.prop('checked', false);
        },
        reverseCheck: function () {
            this.each(function () {
                this.checked = !this.checked;
            });
        }
    });
    

    <input type="checkbox" name="items" value="足球"/>足球
    <input type="checkbox" name="items" value="篮球"/>篮球
    <input type="checkbox" name="items" value="羽毛球"/>羽毛球
    <input type="checkbox" name="items" value="乒乓球"/>乒乓球
    <br/>
    <input type="button" id="checkedAllBtn" value="全 选"/>
    <input type="button" id="checkedNoBtn" value="全不选"/>
    <input type="button" id="reverseCheckedBtn" value="全反选"/>
    

    // 测试扩展jQuery对象的方法
    var $items = $(':checkbox[name=items]');
    $('#checkedAllBtn').click(function () {
        $items.checkAll();
    });
    $('#checkedNoBtn').click(function () {
        $items.unCheckAll();
    });
    $('#reverseCheckedBtn').click(function () {
        $items.reverseCheck();
    });
    

![29](https://img-blog.csdnimg.cn/img_convert/b1398a9e45d230003dfc5503c7db6486.gif)

第五章 jQuery项目百练
--------------

### 5.1、项目百练介绍

这一章一共提供了100道练习，源码请在配套资料中获取，这些练习均是作者早期的练习、兼容性代码、CSS特效、精品收藏等等，仅供参考，有精力朋友的可以看看，可能有些写法不是很标准或者您有更好的方案，可以直接在评论区留言，大家一起学习！

### 5.2、项目百练目录

*   Sample0001-美女相册.zip
*   Sample0002-兼容性代码.zip
*   Sample0003-精美选项卡.zip
*   Sample0004-百度首页换肤功能.zip
*   Sample0005-带复选框表格.zip
*   Sample0006-兼容性代码.zip
*   Sample0007-兼容性代码.zip
*   Sample0008-获取节点或者元素.zip
*   Sample0009-验证密码强度.zip
*   Sample0010-百度首页搜索项目.zip
*   Sample0011-模拟星空.zip
*   Sample0012-美女时钟.zip
*   Sample0013-定时阅读协议.zip
*   Sample0014-动态创建表格.zip
*   Sample0015-滑动式轮播图.zip
*   Sample0016-小汽车动画.zip
*   Sample0017-渐入式轮播图.zip
*   Sample0018-捉迷藏动画.zip
*   Sample0019-吸附式导航栏.zip
*   Sample0020-滑动式导航栏.zip
*   Sample0021-旋转式轮播图.zip
*   Sample0022-手风琴案例展示.zip
*   Sample0023-开机小助手动画.zip
*   Sample0024-筋斗云案例.zip
*   Sample0025-美丽的天使.zip
*   Sample0026-可拖拽对话框.zip
*   Sample0027-放大镜效果.zip
*   Sample0028-自定义滚动条.zip
*   Sample0029-贪吃蛇.zip
*   Sample0030-扁平化二级菜单.zip
*   Sample0031-选戏子.zip
*   Sample0032-手风琴选项卡.zip
*   Sample0033-淘宝精品展示.zip
*   Sample0034-选项卡公告栏.zip
*   Sample0035-精美购物车插件.zip
*   Sample0036-呼吸灯轮播图.zip
*   Sample0037-仿小米手风琴展示.zip
*   Sample0038-音乐导航栏.zip
*   Sample0039-城市选择框.zip
*   Sample0040-文字弹幕效果.zip
*   Sample0041-钢琴案例.zip
*   Sample0042-小火箭返航案例.zip
*   Sample0043-五角星评分案例.zip
*   Sample0044-懒加载图片案例.zip
*   Sample0045-仿淘宝首页轮播图.zip
*   Sample0046-仿京东首页轮播图.zip
*   Sample0047-仿360安全换机.zip
*   Sample0048-拖拽旋转相册.zip
*   Sample0049-仿百度经验时光轴.zip
*   Sample0050-照片墙案例.zip
*   Sample0051-瀑布流加载案例.zip
*   Sample0052-旋转翻页案例.zip
*   Sample0053-立体图片翻转特效.zip
*   Sample0054-鼠标不同方位移入特效.zip
*   Sample0055-省市县三级联动.zip
*   Sample0056-抽屉式手风琴.zip
*   Sample0057-仿厅客世界.zip
*   Sample0058-兼容性开发模板.zip
*   Sample0059-仿腾讯新闻多图序列展示.zip
*   Sample0060-3D分块旋转轮播图.zip
*   Sample0061-仿优酷TV轮播图.zip
*   Sample0062-仿商品参数选购.zip
*   Sample0063-仿w3school首页.zip
*   Sample0064-仿家有易购电商首页.zip
*   Sample0065-网页新功能提示案例.zip
*   Sample0066-鼠标点击展开详情.zip
*   Sample0067-组件排序案例.zip
*   Sample0068-仿职位发布案例.zip
*   Sample0069-仿迅雷首页.zip
*   Sample0070-后台侧栏导航.zip
*   Sample0071-弹性广告栏.zip
*   Sample0072-照片墙案例.zip
*   Sample0073-仿京东商品图片展示.zip
*   Sample0074-仿AppIntro首页.zip
*   Sample0075-Material Design Icons.zip
*   Sample0076-英语之家.zip
*   Sample0077-鲜来鲜往.zip
*   Sample0078-麦子学院.zip
*   Sample0079-Material Design Color.zip
*   Sample0080-Java关键字.zip
*   Sample0081-浏览历史静态页面案例.zip
*   Sample0082-小灯泡开关案例.zip
*   Sample0083-百度折叠案例.zip
*   Sample0084-计算器.zip
*   Sample0085-计算器.zip
*   Sample0086-judge\_online\_system.zip
*   Sample0087-选项卡01.zip
*   Sample0088-选项卡02.zip
*   Sample0089-焦点轮播图.zip
*   Sample0090-抽奖活动.zip
*   Sample0091-抽屉式信息栏.zip
*   Sample0092-无缝轮播图.zip
*   Sample0093-Attendance.zip
*   Sample0094-统计数字.zip
*   Sample0095-反转字符串.zip
*   Sample0096-表单验证.zip
*   Sample0097-显示时间.zip
*   Sample0098-扁平化选项卡.zip
*   Sample0099-吃热狗小游戏.zip
*   Sample0100-爱阅读APP.zip
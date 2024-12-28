 

Django 是用Python开发的一个免费开源的Web框架，可以用于快速搭建高性能，优雅的网站！采用了MVC的框架模式，即模型M，视图V和控制器C，也可以称为MVT模式，模型M，视图V，模板T。

在学习Django的过程中将学到的知识进行总结分享出来，温故而知新，如果能帮助到想学Django但不知道如何开始的同学是再好不过了。

开始前的准备工作
--------

### 搭建虚拟环境

随着我们项目的积累，有时候不同项目需要用不到不同版本的包，可能会产生冲突，这时候我们需要一个虚拟环境将每个项目需要的包进行独立，这样就能有效避免冲突。

### 安装MySql

Django支持很多中类型的数据库，默认配置的sqlite3，在学习过程中我们用到了Mysql  
安装Python3、pip、PyCharm

Django2.0和以后的版本不再支持Python2.X，所以我们需要安装Python3.6版本的解释器。  
pip是一个通用的Python包管理工具，可以对包进行查找、安装、卸载  
PyCharm是一种Python IDE，墙裂推荐。

以上准备工作，小伙伴们可以自行网上查找相关教程。

### 初探Django

通过准备工作我们的系统中已经安装pip，通过使用pip安装最新版的Django。

    pip3 install django


安装完成之后我们可以通过 python3 -m django --version 查看当前Django版本

    (django_venv) xxxAir:djangoDemo xxx$ python3 -m django --version
    2.1.3


### 创建一个Django项目

1、我们可以通过终端输入命令行创建一个项目

这里我的项目名为 djangoDemo

    django-admin.py startproject djangoDemo


2、也可以通过pycharm的create new project进行创建  
![在这里插入图片描述](https://img-blog.csdnimg.cn/4da9f46c13a6417cbea764a9c4ef9f74.png#pic_center)

**查看Django项目的目录结构**

切换终端到项目所属目录，使用tree命令可以查看项目结构

    mac安装tree:        brew install
    ubuntu安装tree:    sudo apt-get install tree
    centos安装tree:     sudo yum -y install tree
    
    执行 「tree + 项目名」
    tree djangoDemo
    
    djangoDemo/
    ├── djangoDemo
    │   ├── __init__.py
    │   ├── settings.py
    │   ├── urls.py
    │   └── wsgi.py
    └── manage.py


目录说明：

1、djangoDemo/djangoDemo: 项目最初的Python包

2、djangoDemo/init.py: 一个空文件，声明所在目录的包为一个Python包

3、djangoDemo/settings.py: 管理项目的配置信息

4、djangoDemo/urls.py: 声明请求url的映射关系

5、djangoDemo/wsgi.py: python程序和web服务器的通信协议

6、manage.py： 一个命令行工具，用来和Django项目进行交互，如前面创建项目就用到了该文件。

### 项目配置文件–setting.py

setting.py 文件用来配置整个项目，里面的字段非常多，所以在开始之前有必要先都了解一下默认的配置有哪些

```py
import os

# 项目的相对路径，启动服务的时候会运行这个文件所在路径的manage.py
BASE_DIR = os.path.dirname(os.path.dirname(os.path.abspath(__file__)))

# 安全密钥
SECRET_KEY = 'l&!v_npes(!j82+x(44vt+h&#ag7io2x&shnf*9^8fv0d63!0r'

# 是否开启Debug
DEBUG = True

# 允许访问的主机ip，可以用通配符*
ALLOWED_HOSTS = []

# Application definition

# 用来注册App 前6个是django自带的应用
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
]

# 中间件 ,需要加载的中间件。比如在请求前和响应后根据规则去执行某些代码的方法
MIDDLEWARE = [
    'django.middleware.security.SecurityMiddleware',
    'django.contrib.sessions.middleware.SessionMiddleware',
    'django.middleware.common.CommonMiddleware',
    'django.middleware.csrf.CsrfViewMiddleware',
    'django.contrib.auth.middleware.AuthenticationMiddleware',
    'django.contrib.messages.middleware.MessageMiddleware',
    'django.middleware.clickjacking.XFrameOptionsMiddleware',
]

# 指定URL列表文件 父级URL配置
ROOT_URLCONF = 'djangoDemo.urls'

# 加载网页模板路径
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]

# WSGI的配置文件路径
WSGI_APPLICATION = 'djangoDemo.wsgi.application'

# 数据库配置 默认的数据库为sqlite
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
    }
}

# 相关密码验证
AUTH_PASSWORD_VALIDATORS = [
    {
        'NAME': 'django.contrib.auth.password_validation.UserAttributeSimilarityValidator',
    },
    {
        'NAME': 'django.contrib.auth.password_validation.MinimumLengthValidator',
    },
    {
        'NAME': 'django.contrib.auth.password_validation.CommonPasswordValidator',
    },
    {
        'NAME': 'django.contrib.auth.password_validation.NumericPasswordValidator',
    },
]

# 语言设置 默认英语， 中文是zh-hans
LANGUAGE_CODE = 'en-us'

# 时区设置，中国的是：Asia/Shanghai
TIME_ZONE = 'UTC'

# i18n字符集是否支持
USE_I18N = True

USE_L10N = True

# 是否使用timezone
# 保证存储到数据库中的是 UTC 时间；
# 在函数之间传递时间参数时，确保时间已经转换成 UTC 时间；
USE_TZ = True

# 静态文件路径
STATIC_URL = '/static/'
复制代码App
接下来要引入一个APP的概念，举个例子我们需要开发一个电商网站，那么产品列表、购物车、下单等等这都是不同的业务线，我们可以把每条业务线都看做一个App。
创建一个名为app_demo的应用,  在终端项目目录下执行
 python3 manage.py startapp app_demo
复制代码再次tree 查看目录结构
├── app_demo
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── migrations
│   │   └── __init__.py
│   ├── models.py
│   ├── tests.py
│   └── views.py
├── djangoDemo
│   ├── __init__.py
│   ├── __pycache__
│   │   ├── __init__.cpython-36.pyc
│   │   └── settings.cpython-36.pyc
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
└── manage.py
```


#### app_demo目录结构

*   admin:对应应用后台管理配置文件
*   apps:对应应用的配置文件
*   models:数据模块，用于设计数据库等
*   tests:编写测试脚本
*   views：视图层，直接和浏览器进行交互

每次新建一个App我们需要将其在settings.py文件中的INSTALLED_APPS里进行注册，这样程序才能够找到这个服务

    INSTALLED_APPS = [
        'django.contrib.admin',
        'django.contrib.auth',
        'django.contrib.contenttypes',
        'django.contrib.sessions',
        'django.contrib.messages',
        'django.contrib.staticfiles',
        'app_demo', # 注册新创建的应用app
    ]


### HelloWorld

helloworld任何一门语言的开始，所以，我们入门的带个程序也从这里开始。前面说过Django框架式MVT结构的，这里由于没有用到数据和模板所以只需要在V(视图层)进行coding。

打开app_demo目录下的view.py， 开始coding

    from django.http import HttpResponse
    """
     django.http模块中定义了HttpResponse 对象的API
     作用：不需要调用模板直接返回数据
     HttpResponse属性：
        content: 返回内容,字符串类型
        charset: 响应的编码字符集
        status_code: HTTP响应的状态码
    """
    
    """
    hello 为一个视图函数，每个视图函数必须第一个参数为request。哪怕用不到request。
    request是django.http.HttpRequest的一个实例
    """
    def hello(request):
        return HttpResponse('Hello World')


视图层写完,最终通过HttpResponse将’Hello World’进行响应。

前面提到过urls是用来声明请求url的映射关系。也就是程序通过urls里的配置来找到我们写的这个view。

    # 导入url模块
    from django.conf.urls import url
    
    urlpatterns = [
        path('admin/', admin.site.urls),
        url(r'^hello/$', views.hello)
    ]


上面的代码就是在djangoDemo下的view文件中加入

    from django.conf.urls import url
    url(r'^hello/$', views.hello)


在urlpatterns中加入url(‘hello/’, views.hello)，第一个元素是匹配的字符串，第二个元素为相对应的视图模块。

也就是告诉django所有url/hello/ 的请求都是指向了views.hello 这个视图。hello前不需要加’/‘,因为域名的末尾一定会有’/‘。其中’^‘为严格前匹配,’,浏览器输入http://localhost:8000/hello/a/b 也是可以访问view.hello视图

再来个栗子

    app_demo的views模块中继续添加(和前面写的hello视图同文件)
    def msg(request, name, age):
        return HttpResponse('My name is ' + name + ',i am ' + age + ' years old')


setting中app_demo这个app前面已经注册过，所以不需要再次注册，在urls配置他们的关系映射

    urlpatterns = [
        path('admin/', admin.site.urls),
        url(r'^hello/$', views.hello),
        url(r'^msg/(?P<name>\w+)/(?P<age>\d+)/$', views.msg)
    ]


这个就是通过正则去匹配我们的url,(?P\\w+) 表示name字段的值范围为非数字的字符即:a-z A-Z 汉字、(?P\\d+) 表示age字段只能是数字

### 启动项目

通过执行如下命令来启动项目

    python3 manage.py runserver 


默认端口号为：8000，当8000端口被占用时，我们也可以手动去更换端口，如更换成8080

    python3 manage.py runserver 8080


控制台输入一下内容则表示启动成功：

    Performing system checks...
    
    System check identified no issues (0 silenced).
    
    You have 15 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions.
    Run 'python manage.py migrate' to apply them.
    
    November 08, 2018 - 05:34:59
    Django version 2.1.3, using settings 'djangoDemo.settings'
    Starting development server at http://127.0.0.1:8000/
    Quit the server with CONTROL-C.


项目启动成功浏览器输入  
`http://localhost:8000/hello/`  
我们可以看到如下界面  
![在这里插入图片描述](https://img-blog.csdnimg.cn/448fe182e2a042bda7fa6de9da76e1fb.png#pic_center)
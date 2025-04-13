

# Flask-----route装饰器详解

```py
'''
  app.py中的源码def route(self, rule, **options)
  @app.route()路由参数使用：
      1.第一个位置参数为路由分发的请求路径
          ①静态参数路由：/index  /   /base 等
          ②动态参数路由:/index/<name> 在路由中使用了<变量名>的路由称为动态路由，
                      动态路由参数<name>会接收字符串和数字类型，但在制定了int时会优先调用该视图
                      可以指定int型，如/index/<int:id>,在视图函数中必须有同名的形参来接收
  
      2.methods=['GET','PosT']
          2.1当前视图函数支持的请求方式（405当前请求方式不被允许），
          2.2参数为可迭代对象，请求方式不区分大小写，不设置默认为GET
  
  
      3.endpoint=''
           3.1路由映射视图函数，endpoint不指定默认为视图函数名（view_func.__name__）
           3.2项目中存储视图函数的view_funcs是以{endpoint:view_func}形式存储，因此视图函数不能同名，
           3.3在使用自定义装饰器时注意指定唯一的endpoint,以避免在多个视图函数使用自定义装饰器时报错；
  
  
      4.defaults={key:value}
          默认参数设置，必须在视图函数中定义一个形参来接收
  
      5.redirect_to=''
          永久重定向（301或者308）
          应用场景：用户之前收藏的是视图函数对应的路由地址，后来页面不在使用，换了新的路径，为了避免用户收藏的不能访问，因此设置永久重定向
  
      6.strict_slashes=True/False
          设置路由路径匹配是否为严格模式，默认不设置为严格路由匹配模式
  
      7.补充小知识：
          falsk中通过视图函数名反向解析请求路径：
              ①from  flask import url_for
              ②url_for('函数名')==>当前视图函数对应的路由请求路径（具体见知识点6）
FBV:app.add_url_rule('/',endpoint='',view_func=func)            	                                                      		 CBV:app.sdd_url_rule('/',endpoint='',view_func=CLASS.as_view(name=''))             
  
'''

from flask import Flask, render_template, request, session, redirect, url_for

app = Flask(__name__)
app.config['DEBUG'] = True
app.secret_key = 'werf23456'

# 1.flaskl路由：
# 1.1静动态路由
@app.route('/index')
def index():
    return f'静态路由请求！'

# 1.2动态参数路由
# 1.2.1动态路由匹配变量
@app.route('/index/<name>')  # http://192.168.16.14:9000/index/yang
def index2(name):
    return f'当前请求的动态参数为：{name}'  # 当前请求的动态参数为：yang

# 1.2.2动态路由变量指定匹配
@app.route('/index/name=<name>')  # http://192.168.16.14:9000/index/name=yang
def index3(name):
    return f'当前请求的动态参数为：{name}'  # 当前请求的动态参数name为：yang

# 1.2.3动态路由整数变量匹配
@app.route('/index/<int:id>')  # http://192.168.16.14:9000/index/1234
def index4(id):
    return f'当前请求的页码为：{id}'  # 当前请求页码为：1234

# 2.methods=[]支持的请求方式参数设置，不设置默认为GET
@app.route('/login', methods=['GET', 'PoSt'])  # 请求参数设置不区分大小写，源码中自动进行了upper
def login():
    if request.method == 'GET':
        return render_template('login.html')
    elif request.method == 'POST':
        username = request.form.get('username')
        pwd = request.form.get('pwd')
        if username == 'yang' and pwd == '123456':
            session['username'] = username
            return 'login successed 200  ok!'
        else:
            return 'login failed!!!'

# 3.endpoint=''路由映射视图函数
'''
自定义装饰器装饰多个视图函数时，如果在路由中没有指定唯一的endpoint,
则所有装饰的视图函数返回的都是装饰器中的inner函数，同名因此会报错
AssertionError: View function mapping is overwriting an existing endpoint function: inner
'''

def auth(func):
    def inner(*args, **kwargs):
        if session.get('username'):
            return func()
        else:
            return '未登录无权访问!'
    return inner

@app.route('/data1', endpoint='data1')
@auth
def data1():
    return '您已登录成功，通过路径/data1来到当前页面!'

@app.route('/data2', endpoint='data2')
@auth
def data2():
    return '您已登录成功，通过路径/data2来到当前页面!'

# 4.defaults={key:value}默认参数
@app.route('/key', defaults={'id': 23})
def key(id):
    return f'路由设置的默认参数值为：{id}'

# 5.redirect_to=''永久重定向（301或者308状态码）
@app.route('/admin', redirect_to='/redirect')
def admin():
    return '原页面'

@app.route('/redirect')
def redi():
    return '访问/admin永久重定向的新页面!'

# 6.strict_slashes=True/False  设置路由路径匹配是否为严格模式，默认不设置为严格路由匹配模式
#（对于在请求路径加了/的路径，在进行路由严格模式匹配时，如果在请求时未加/，flask会进行返回308加上/重定向）

#6.1不设置strict_slashes默认未严格模式，在路由后边没有/s时，如果访问加上就会报错404
@app.route('/strict_true', strict_slashes=True)
def strict_true():
    return f'严格模式匹配{url_for("strict_true")}'

#6.2指定strict_slashes=False非严格模式时，，在路由后边加/依然可以正常映射
@app.route('/strict_false/', strict_slashes=False)
def strict_false():
    return f'非严格模式路由匹配{url_for("strict_false")}'

if __name__ == '__main__':
    app.run('0.0.0.0', 9000)
```


 

### 简介

最近用了将近一周的时间，做了一个我也不知道有啥用的东西----Python爬虫(京东)。

当然重点不是这，相信不少像我这样的菜鸟在用Python弄爬虫项目的时候，遇到最痛苦的就是被验证码拦在了门外，我也是花了好几天的时间去研究，终于解决了这一难关。

需要源码的小伙伴复制下面即可，有闲心情的可以继续看下去，听我叭叭几句（哈哈），记得把位置坐标啥的换了哈，还需要有selenium 火狐的插件，大家可以百度一下。

    from urllib import request
    from selenium import webdriver
    import cv2
    import random
    import time
    import pyautogui
    
    
    # 获取图片信息，返回最佳匹配位置
    def findPic(target="img1.jpg", template="img2.png"):
        # 读取图片
        target_rgb = cv2.imread(target)
        # 图片灰度化
        target_gray = cv2.cvtColor(target_rgb, cv2.COLOR_BGR2GRAY)
        # 读取模块图片
        template_rgb = cv2.imread(template, 0)
        # 匹配模块位置
        res = cv2.matchTemplate(target_gray, template_rgb, cv2.TM_CCOEFF_NORMED)
        # 获取最佳匹配位置
        value = cv2.minMaxLoc(res)
        # 返回最佳X坐标
        return value[2][0]
    
    
    # 打开FireFox浏览器
    driver = webdriver.Firefox()
    driver.get("https://passport.jd.com/new/login.aspx")
    driver.find_element_by_xpath('/html/body/div[2]/div[2]/div[1]/div/div[3]/a').click()
    driver.find_element_by_xpath('//*[@id="loginname"]').send_keys('123456')
    driver.find_element_by_xpath('//*[@id="nloginpwd"]').send_keys('123456')
    driver.find_element_by_xpath('//*[@id="loginsubmit"]').click()
    
    while True:
        try:
            # 从网页上获取组件
            target = driver.find_element_by_xpath('/html/body/div[4]/div/div/div/div[1]/div[2]/div[1]/img')
            template = driver.find_element_by_xpath('/html/body/div[4]/div/div/div/div[1]/div[2]/div[2]/img')
            # 获取模块的url路径
            src1 = target.get_attribute("src")
            src2 = template.get_attribute("src")
            # 下载图片
            request.urlretrieve(src1,"img1.jpg")
            request.urlretrieve(src2,"img2.png")
            x = findPic()
            w1 = cv2.imread('img1.jpg').shape[1]
            w2 = target.size['width']
            x = x / w1 * w2
            # 按钮坐标
            offset_x,offset_y = 875,466
            # pyautogui库操作鼠标指针
            pyautogui.moveTo(offset_x,offset_y,duration=0.1 + random.uniform(0,0.1 + random.randint(1,100) / 100))
            pyautogui.mouseDown()
            offset_y += random.randint(9,19)
            pyautogui.moveTo(offset_x + int(x * random.randint(15,25) / 20),offset_y,duration=0.28)
            offset_y += random.randint(-9,0)
            pyautogui.moveTo(offset_x + int(x * random.randint(17,23) / 20),offset_y,
                             duration=random.randint(20,31) / 100)
            offset_y += random.randint(0,8)
            pyautogui.moveTo(offset_x + int(x * random.randint(19,21) / 20),offset_y,
                             duration=random.randint(20,40) / 100)
            offset_y += random.randint(-3,3)
            pyautogui.moveTo(x + offset_x + random.randint(-3,3),offset_y,duration=0.5 + random.randint(-10,10) / 100)
            offset_y += random.randint(-2,2)
            pyautogui.moveTo(x + offset_x + random.randint(-2,2),offset_y,duration=0.5 + random.randint(-3,3) / 100)
            pyautogui.mouseUp()
            time.sleep(1)
            result = driver.find_element_by_xpath('/html/body/div[2]/div[2]/div[1]/div/div[4]/div[2]/div').text
            if '不匹配' in result:
                print("账户名密码不匹配!", result)
                break
        except:
            print("异常!")
            break
    

### 技术

> selenium

网上都说selenium是一个自动化测试的类库，其他的先不说，selenium用在爬虫上是真的般配，用selenium实现模拟的登陆，操作页面上的各种组件，完全代替了人工，简直神器啊，细节我就不说了，初学的小伙伴可以先去了解一下selenium库。

账号输入，点击之后就是验证码的界面，这个时候就需要另一个神器了。

> opencv

opencv是Python第三方库，处理计算机视觉方面。

验证码登陆必须要进行图像处理，借用京东的滑块验证码来说明一下。

我们只需要封装一个函数，在之前selenium操作显示出验证码之后，通过页面解析获取验证码的图片和滑块的图片（2张都要，下面简称大图和小图），  
然后图像灰度处理，找出大图的缺口的位置，注意点就是图片和网页上的比例，还有就是图片是否有边界，总之就是找出在页面上滑块应该移动的距离。

找出距离之后就是移动滑块了，通过selenium移动就可以完成整个流程了。

虽然selenium执行滑块移动完全没有问题，但是对于京东的官网（毕竟是互联网大厂），滑块移动到指定位置之后，验证也无法通过，大概原因就是selenium执行会被检测出来，不得不说京东的反爬虫处理是真的严格，这个时候就需要另一个神器了。

> pyautogui

说实话，pyautogui也是真的nb，实现自动化控制鼠标键盘的行为，好像不少的脚本外挂都与pyautogui有关。

继续上面说的，我们获取到滑块应该移动的距离之后，不再使用selenium，而是用pyautogui代替，完全模拟认为的操作，值得一提的是，用pyautogui执行滑块移动时，我们需要多设置几次，一下子就移动到指定位置也是行不通的，我设置的是移动4次，并且每次的距离和时间都是随机生成的，就这样，通过率也是很高，不得再说一次，京东NB。

就这样，搞了个这么不知道有啥用的东西，仅以本次文章记录一下这几天的成果吧！  
欢迎各位前辈大佬指点不足，fignting！
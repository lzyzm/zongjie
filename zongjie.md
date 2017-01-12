# 日常总结 

标签（空格分隔）： 未分类

---
##Git部分
常用命令
\$ mkdir runoob  **创建文件夹**
\$ cd runoob **切换进入**
\$ Git init **初始化仓库**
\$ Git clone url **克隆项目**
\$ ls **查看文件**
\$ git add file **添加文件到缓存区**
\$ git status -s **检查工作区间状态  -s简单输出**
\$ vim file **编辑文件**
\$ git diff **显示具体改动、、查看尚未缓存的改动**
\$ git diff --cashed **查看已经缓存的改动**
\$ git reset HEAD file **取消已缓存的所有改动**
\$ git branch (branchname) **创建分支**
\$ git checkout (branchname) **切换分支**
\$ git merge **合并分支**
\$ git branch -d (branchname) 删除分支命令
\$ git log **查看提交历史**
\$ git log --oneline **查看简洁版本历史**
\$ git log --reverse --oneline **逆向显示日志**
\$ git tag -a v1.0 **打上标签**
\$ git tag **查看标签**
\$ git checkout -b (branchname) **创建并切换分支**
\$ git remote add (origin) (master) **添加远程仓库**
\$ git remote **查看当前配置有哪些仓库**
\$ git fetch **从远程仓库下载新分支与数据**
\$ git pull **从远程仓库提取数据并尝试合并到当前分支**
\$ cat file **查看文件内容**
\$ git push origin branch **推送你的新分支与数据到某个远端仓库**
\$ git remote rm 别名  **删除远端仓库**
\$ git reset --hard HEAD^ **返回上一个版本**
\$ git reset --hard HEAD^^ **返回上上个版本**
\$ git reset --hard HEAD commit_id **指向id进行指向跳转**
\$ git reflog **显示记录每一条命令含id**
\$ git checkout -- file **把工作区的修改全部撤销让文件回到最后一次Git commit或git add状态**
\$ git reset HEAD file **把暂存区的修改撤销掉**
\$ git push -u origin master **推送到远程（-u本地master分支和远程master分支关联起来）**
\$ git stash **把当前工作现场存储起来**
\$ git stash list **查看存储**
\$ git stash apply **恢复存储**
\$ git stash drap **删除存储**

##h5wep
---
###html5八大新特性
1.语义网——语义化标签
2.离线&存储  APP-cache  localStorage sessionStorage
3.设备访问——Geolocation API   orientation API
4.通信   web socket
5.多媒体   video  audio
6.图形与特效  SVG canvacs  WebGL  2D/3D
7.性能和集成  webworker
8.显示css3
***
###h5全局属性
1.**contentEditable**    contentEditable=“true”可编辑模式，实现功能需借助document.execCommand函数
如document.execCommand("bold")加粗       获取当前id  e.currentTarget.id
2.**contentmenu**   定义原生右键菜单
    menu菜单元素含有label属性type属性类型有context、toolbar和list，该元素可以嵌套中间可以包含li元素或者menuitem元素
3.**draggable和dropzone**属性    draggable属性使元素具有被拖拽能力，dropzone属性给元素提供放置被拖拽元素的能力
4.**hidden**属性
5.**data-\***属性
    data属性可以使用自定义的属性方式来存储数据,所有浏览器都支持
```
<div class="spaceship" data-ship-id="92456">
```
    可以使用getAttribute方法来获得data-属性值，setAttribute属性设置其值
```
    console.log(el.getAttribute("data-ship-id"))=>92456
    el.setAttribute("data-ship-id","92456")
```
    还可以在javascript中通过dataset属性访问data-属性值 
```
    console.log(el.dataset.ship-id)//不用加data-
    el.dataset.ship-id="92456"//设置
```
    如果需要删除一个值，将其置为null，或者使用delete
```
    el.dataset.ship-id=null
    delete el.dataset.ship-id
```
    在jquery中data方法也可以访问data-属性，还可以自动反序列话JSON
```
    $("#id").data("ship-id")
```
    很多javascript库使用data-属性来进行组件或者API定义，bootstrap中同样使用data-api风格 
***
**iframe标签**
为创建框架式网页获取嵌入外部网页，现该标签存在安全策略，被视为独立的源，且不能提交表单也不能执行javascript，无法控制符页面导航行为
如想修改安全策略，可以在sandbox属性中使用预定义的字符串
-allow-same-origin：允许嵌入内容访问遵循同源策略的资源，如本地存储、cookie和XHR等
-allow-top-navigation:允许嵌入的页面对顶层页面进行导航
-allow-forms:允许嵌入内容提交表单
-allow-scripts：允许嵌入页面执行脚本代码
***
##HTML 5表单
获取表单字段的值
```
var email=this.elements.namedItem("email").value.trim();
var phone=this.elements.namedItem("phone").value.trim()
```
input元素和其属性
属性：placeholder、pattern、autofocus、autocomplete等
输入类型：email、url、url、search、color、number、range、data
当类型是number时，在javascript中可以使用valueASNumber来得到number对象，其含有min,max,step属性
当类型是file当无法上传的时候需指定multiple属性，可以指定accept属性过滤文件类型---audio/*、video/*、image/*类型
**form表单操作**
增加了autocomplete和novalidate两个属性，后者表示提交时不用验证
增加form属性，可以应用到大多数表单元素上，包括select，textarea，output，keygen和fieldest等，
还增加了几个表单相关的元素，meter，progress，output，keygen
***
##css初探
margin对于table相关类型的元素是不起作用的，如td,tr,th
margin/存在外边距折叠现象，根据margin的正负存在几个规则：
1.当这些margin均为正值时，取margin中最大的最大值；
2.当margin中正负都存在时，先取出负margin中的绝对值最大的，然后和正margin值中最大的margin相加。
**表格3要点：**
1.表格元素的匿名机制：渲染结构总是有cell/row/row group/column/colmn group和table这6部分
2.表格的布局机制：表格的宽度布局算法有两种，一种是固定，一种是自动，可以使用table-layout属性指定（auto/fiexd）
3.表格的边框：在于掌握border-collapse属性-一种是边框分离模型，这种模型下每个单元格以及table边框都是独立的，此时可以使用border-spacing属性指定单元格边框距离border-collapse：separate----一种是边框合并模型，使用border-collapse：collapse来指定
**选择器的增加**
1.属性选择器
2.结构性伪类选择器：：nth-child和nth-of-type的区别
**背景：**
background-size有两个关键字cover和contain.cover用于等比扩展图片来填满元素，即用图片覆盖住元素。contain则是等比缩小图片来适应元素，即让元素容纳整个图片。
background-origin背景绘制起始区域，background-clip背景裁剪起始区域，他们都可以指定border-box、padding-box、和content-box；；；可以应用背景不想覆盖住padding时，可以设置
**渐变和阴影**
线性渐变和径向渐变
线性：
```
#div{background:-webkit-linear-gradient(to,black,white)}
#div1{background:-webkit-linear-gradient(45deg,black,white)}
#div2{background:-webkit-linear-gradient(gray,black,white,yellow)}
```
径向：
```
#div{background:-webkit-radial-gradient(bottom,circle,black,gray 20%,black 40%,white 60%)}
circle表示渐变成正圆，相应ellipse非正圆，
```
线性渐变和径向渐变都不会自动重复，存在repeating-linear-gradient和repeating-radial-gradient属性提供重复
```
#div1{background:-webkit-repeating-linear-gradient(-45deg,black,black 5px,white 5px,white 10px)}
#div1{background:-webkit-repeating-radial-gradient(circls,black,black 5px,white 5px,white 10px)}
```
阴影：
一类是文字阴影text-shadow：1px 1px 4px gray，
```
text-shadow:-1px 0px 0px gray,
             1px 0px 0px gray,
             0px -1px 0px gray,
             0px 1px 0px gray;
```
一类是盒阴影box-shadow:1px 1px 5px gray
**css3布局**
1.负边距与浮动（双飞翼布局）
2.栅格系统与多列布局
多列布局模块：
```
-webkit-column-count:2//列数
-webkit-column-width：10em//列宽
-webkit-column-gap:5em//列与列中间缝隙
-webkit-column-rule:6px solid blue//列中间的分割线
```
3.弹性盒模型（Flexible Box）
a.弹性容器（flex container）
display属性为flex或为inline-flex的元素将变成一个弹性容器
b.弹性项
弹性容器内的子元素自动成为可供布局的弹性项
c.轴线
默认情况下弹性容器中的子元素将在水平上排布，通过设置flex-flow属性来改变，可以设置为row/row-reverse/column/column-reverse四种值
d.方向（derections）
弹性项可以使用order属性指定出现顺序
e.尺寸（Dimensions）
flex属性
e.尺寸（）
**css3动画**
1.css变形
transform和transform-origin是css变形最主要的两个属性，transform指定要对元素进行哪些变形，transform-origin则指定变形的起始位置
transform包含rotate、skewx、translate、scale函数，分别可以接受x/y/z三个值，3D：rotate3d；
（1）**透视（perspective）**
次理解3d变形的关键，-webkit-transform-style:preserve-3d指定元素在3d空间内的定位
-webkit-perspective-origin：-100% -50%指定用户从哪个方向看过来
**animation**
animation多个属性的集合：
animation-delay：动画开始前的延迟；
animation-duration:动画时长；
ainmation-iteration-count：动画重复次数，设置为infinite为无限动；
animation-name：要使用的动画名；
animation-direction：动画方向，值有reverse，alternate（往复运动），alternate-reverse
animation-timing-function:缓动函数-ease（先慢后快再慢），ease-in（先慢后快），ease-out（先快后慢），linear（线性）
animation-dill-mode:通过设置forwards、backwarks和both可以将元素最终状态设置为动画的起始或结束状态
animation提供了一些事件用以控制动画，animationstart：动画开始时触发；animationend：动画结束时触发；animationiteration：动画每迭代一次触发一次改事件
**响应式设计**
PPI：像素密度，每英寸的像素数量，及为PPI值。
设备像素比：物理分辨率/逻辑分辨率的比值。retina设备的像素比2、1.5。在javascript里通过访问window.devicePixelRatio的值来确定
可见视口和布局视口
media queries---书写样式
```
@media all and (max-width:320px) and (-webkit-min-device-pixel-radio:2){
    /*在这里编写针对 iphone retina屏幕的代码*/
}
```
media queries规则还可以直接写到link元素的media属性中,可以按需加载css文件
```
<link rel="stylesheet" href="wide.css" media="screen and (min-width:1024px)">
```
在javascript中也可以使用media queries，DOM中提供了接口，方法
```
var mql=window.matchMedia("(orientation:portrait)")
```
**WEB**
cookie通过封装函数setCookie和getCookie来操作具体的cookie；
encodeURIComponent（编码）和decodeURIComponent（解码）
cookie限制：浏览器在cookie数量上的限制，大小的限制
web Storage:
sessionStorage中存储的数据只在单个页面的会话期间有效，localStorage的数据则会被持久化到客户端
localStorage.setItem("name","liming")
localStorage.getItem("name")
localStorage.removeItem("name")
如果要存储JSON对象，使用window.Json对象提供的stringify和parse进行JSON数据的序列化和反序列化
**storage事件**
监听该事件
domain:发生变化的域名
key:发生修改的键
oldValue：修改前的值
newValue：修改后的值
```
document.addEventListener("storage",function(e){
    console.log("Storage changed.Name'"+e.key+"'changed form'"......)
    //存在兼容性，不建议使用
})
```
IE的userData
**离线应用**
h5提供缓存机制:Application Cache(应用缓存)
基本使用
```
<!DOCTYPE html>
<html manifest="/appcache.manifest">
//这个html本身一定会被缓存
</html>
```
appcache.manifest其实就是一个文件，指定了需要浏览器缓存的资源，
```
CACHE MANIFEST
index.heml
/favicon.ico
images/logo.png
//必须在有网络时才能访问的资源
http://api.weibo.com
FALLBACK
//所有images目录下的文件不可用时被请求，则读取images/offline.jpg
images/images/offline.png
```
更新缓存方法：
编程接口：通过javascript访问离线缓存接口，window.applicationCache对象定义了应用缓存的接口，applicationCache.update()方法检测更新，当下载完调用applicationCache.swapCache()完成更新缓存，使用applicationCache.status属性查询缓存当前状态；
***
**拖放**
事件对象中target对象和currentTarget对象的区别：
1、target在事件流的目标阶段；currentTarget在事件流的捕获，目标及冒泡阶段。 
2、event.currentTarget指向事件所绑定的元素，而event.target始终指向事件发生时的元素。 
3、事件真正的发送者是evt.target（而且是可以变的，根据触发的不同displayObject），注册侦听器的是evt.currentTarget（不会变的）。 
4、在 Google 浏览器内，同时拥有 srcElement 和 target 这两个标签，这两个标签本质相同，但在 FireFox 浏览器里面却没有 srcElement 标签，如果使用了 srcElement 标签，将导致不兼容 FireFix 浏览器，所以别被用错一个标签导致浏览器不兼容给坑了。
在需要通过一个函数处理多个事件时，可以使用type属性

拖拽相关的事件
ondragstart：此事件在用户开始拖动元素或选择文本时触发 ondrag:元素正在拖动时触发 ondragend:用户完成元素拖放时触发 ondragleave:当被鼠标拖动的对象离开其容器范围时触发 ondragover:当某个被拖动的对象在另一对象容器范围内拖动时触发此事件，此事件发生在目标元素身上 ondrop:在一个拖动过程中，释放鼠标时触发，此事件作用在目标元素身上

dataTransfer 对象相关方法
setData(format,data):添加自定义数据格式 getData(format):获取自定义的数据格式clearData([format]):清除自定义的数据格式及数据
***
**文件操作**
File API是HTML5在DOM标准中添加的功能，它允许WEB内容在用户授权的情况下选择本地文件并读取他们的内容----通过File、FileList和FileReader等对象共同作用来实现。
file表单可以让用户选择一个或多个（multiple属性）
file对象有三个属性：name文件名，size文件大小，type文件的MIMEtype
拖拽文件使用e.dataTransfer.files;
**FileReader**对象
可以将文件对象转换为字符串、DataURl对象或者二进制字符串
e.tatget.result包含读取为dataURL信息
reader.readAsDataURL(file)此方法讲file对象读取为dataURL。
readAsDataURL方法用于读取文件他接受一个file或Blob对象实例作为参数，并将文件内容转换为一个base64编码的URL字符串，并通过load事件讲结果e.target.result上。
除了load事件FileReader对象还会调用这样一些事件程序：
1.onabort：当读取操作被终止时调用
2.onerror：当读取操作发生错误时调用
3.onload:当读取操作完成时调用
4.onloadend：当读取操作完成时调用，不管成功还是失败
5.onloadstart:当读取操作将要开始之前调用
5.onprogress：在读取数据过程中周期性调用
onprogress是最有用的，可以设置进度条：e.total存储着当前文件总大小，e.loaded表示当前文件已经加载了多少
***
**touch事件**
touch事件模型现阶段规定了很多类型触摸事件，下面三种应用最广泛
1.touchstart：手指刚放到屏幕上某个DOM元素里的时候改元素触发。
2.touchmove：手指紧贴屏幕移动的时候连续触发。
3.touchend：手指从屏幕上抬起的时候触发。
触摸事件对象包含一些工通的时间属性：
1.touches:表示当前位于屏幕上的所有手指动作的列表，是一个TouchList类型的对象，ToushList是一个类数组对象，里面装的是Touch对象
2.targetTouches：位于当前DOM元素上的手指动作的TouchList列表
3.changedTouches：涉当前事件的手指动作的列表
Touch对象包含属性：
1.identifier：一个数字，用于唯一标识触摸会话中的当前手指
2.target:作为动作目标的Dom元素
3、坐标、clientX/clientY触摸点相对浏览器窗口viewport的位置，pageX/pageY触摸点相对于页面的位置，screenX/screenY:触摸点相对于屏幕的位置

hammer.js手势库，几乎支持所有手势，Tap、DoubleTap；
backface-visibility属性意思是在对元素进行变换时，如果元素的“正面看不见了，那么就隐藏整个元素hidden”









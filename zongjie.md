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
\$ git remote add (origin) (master) **添加到远程仓库**
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









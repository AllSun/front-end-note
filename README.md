# 工具使用

## vscode快捷键

`cmd+/`  注释

`cmd + shift + f` 格式化

`cmd + alt + 方向键`  复制一行

`ul.classname>li.classname*n` 快速生成n个无序列表

`.classname` 快速生成div类名为classname

`cmd + shift +k`删除当前行

`ul.li*5>a[href=#]>i.iconfont+{标签内容}`

## Typora快捷键

cmd  1-6  标题

cmd+opt+t   表格

|      |      |      |
| ---- | ---- | ---- |
|      |      |      |

 代码块  esc下方按键 ~~~ 

~~~html
<html>
</html>
~~~

单行代码强调 esc下方按键 ··

`hello world`

斜体 一个*  内容一个 *  

粗体 两个*  内容两个 *

无序列表 -加空格

- 无序

有序列表：数字小数点空格

1. 哈哈哈
2. 图片 

````+语言`可生成代码块

`cmd+/`可以查看各种格式的快捷键

尽量不要使用图片，因为没有上传服务器

## git常用命令

`git config --list`  设置账户信息
`git config --global user.name 'allsun'`
`git config --global user.email '869472104@qq.com'` 

`git init `

工作区、暂存区、版本库
理解为什么要有暂存区：1.可以针对专门任务统一提交，如都是修bug，然后一起提交；2.批量提交想要修改的文件；3.工作区文件变更，想恢复成暂存区的内容，暂存区相当于变成了历史快照，`git restore 文件名`

`git rm --cached 文件名`  删除暂存区的更改

`git add`

`git status -s` 查看文件状态

`git commit -m "变更内容"`    本地仓提交

`git ls-files`查看被追踪的文件

`git reflog --oneline`查看完整历史

`git log --oneline`提交历史记录

`git reset --hard 版本号` 还有soft、mixed模式

`git branch 分支名`创建分支

`git merge 分支名`先要切换为要合并的分支，一般切换为master

`git rebase 分支名`变基合并

**理解merge和rebase**

- merge保留分支合并后创建新的提交，rebase合并成一条主线
- 两种不同合并模式

**合并发生冲突时，手动解决冲突，再commit提交后才能继续使用**

`git branch -d 分支名`合并完就删除

![image-20250303103634267](README.assets/image-20250303103634267.png)

**master原先是C5，合并了新的提交后移动到C10,但是原C5的节点有新的分支，再合并的时候会自动产生C11节点**

`git checkout 分支名`head指针切换到该分支，head指针影响暂存区和工作区的代码

`git remote add origin https://github.com/AllSun/note.git`   与远程仓库进行关联

`git remote remove origin`删除远程仓库

`git push --set -upstream origin master  `    关联上游分支

`git pull --rebase`  远程分支和本地分支没有关联关系的合并

`git pull`  git pull 远程仓库名 远程分支名：本地分支名

`git push`



# 浏览器渲染

```javascript
输入 URL → DNS解析 → TCP连接 → 发送HTTP请求 → 响应返回HTML
→ 浏览器解析HTML → 构建DOM树 → 解析CSS → 构建CSSOM树
→ DOM + CSSOM → 构建渲染树 → 布局（Layout）→ 绘制（Paint）→ 合成（Composite）→ 页面呈现

```

# HTML+CSS

## 常用html标签

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <!-- 移动设备上以设备宽度显示 -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- seo优化   -->
    <!-- 指定网站的关键词 -->
    <meta name="keywords" content="">
    <!-- 指定网站的描述信息 -->
    <meta name="description" content="">
    <link rel="stylesheet" href="./my.css">
    <title>常见标签及解释</title>
</head>
<body>
    <!--h5 当属性和属性值相同时，则可以用一个单词表示-->
    <audio src="#"  controls loop autoplay ></audio>
    <div style="color: red; font-size:20px;">这是 div 标签</div>
    <vedio src="#" controls loop muted autoplay></vedio>
    <strong>加粗</strong>
    <!-- 双标签和单标签 -->
    <!-- 单标签 -->
    <!-- src中分为相对路径和绝对路径，绝对路径就是写死地址 -->
    <img src="" alt="图片挂了，显示的信息">
    <em>斜体</em>
    <i>斜体</i>
    <b>加粗</b>
    5<sup>2<sup>=25 <br>
    H<sub>2</sub>O
    <ins>下划线</ins>
    <del>删除线</del>
    <p>这个标签会换行，当文本内容塞不下会换行</p>
    <hr>这是一条横线分割
    <br>
    <blockquote>长引用</blockquote>
    <q>短引用</q>
    <ul>
        <li></li>
    </ul>
    <ol>
        <li></li>
    </ol>
    <dl>
        <dt>第一阶段</dt>
        <dd>css</dd>
        <dd>html</dd>
        <dt>第二阶段</dt>
        <dd>javascript</dd>
        <dd>vue</dd>
    </dl>
    <div>
        回车不换行，换行当做一个空格处理
        连续多个空格，当做一个空格处理
    </div>
    <div>
        主要用于布局，划分区域
    </div>
    <span>用于解决局部部件、文本</span>
    <!--h1一般网页中只用一次-->
    <h1>h1-h6</h1>
    <!-- href:
    1、可以是网址
    2、可以是工程中的其他文件
    3、可以是页面中的元素，如跳转到类名为footer的标签
    target:
    _self 当前窗口打开
    _blank 新窗口打开 -->
    <a href="wwww.baidu.com" target="_blank">超链接</a>
    <a href=""><img src="" alt=""></a>
    
    <!-- 转移字符 -->
    &ltabc&gt
    &copy

    <!-- 表格  -->
    <table>
        <caption>板块</caption>
        <thead>
            <th>排名</th>
            <th>股票名</th>
            <th>涨幅</th>
        </thead>
        <tbody>
            <tr>
                <!-- td 当中行合并 rowspan=2 列合并colspan -->
                <td>1</td>
                <td>龙头股份</td>
                <td>10%</td>
            </tr>
        </tbody>
        <tfoot></tfoot>
    </table>
  <!--表单 checked（针对radio、checkbox）,multiple(针对file)-->
  <input type:"file/checkbox/radio/text/password" checked placeholder="" multiple>
  <textarea></textarea>
  <label for="man">男</label>
  <selection>
  	<option>北京</option>
    <option>福州</option>
    <option selected>三明</option>
  </selection>
  
  <!-- form 表单区域 -->
<!-- action="" 发送数据的地址 -->
<form action="">
  用户名：<input type="text">
  <br><br>
  密码：<input type="password">
  <br><br>

  <!-- 如果省略 type 属性，功能是 提交 -->
  <button type="submit">提交</button>
  <button type="reset">重置</button>
  <button type="button">普通按钮</button>
</form>
</body>
</html>
~~~

## css知识点

### 常见属性

~~~javascript
height
width
background-color
color
font-family
font-size
font-style  normal/italic
line-height
text-indent  2em  缩进
text-align
text-decoration  underline/linethrough
background-image: url(./images/1.png);
background-repeat: no-repeat;
background-position: 50px center;  水平   垂直
background-size:cover/contain
background-attachment: fixed;
~~~

**font: 是否倾斜  是否加粗  字号/行高 字体（必须按顺序书写）**

**属性值：背景色 背景图 背景图平铺方式 背景图位置/背景图缩放  背景图固定（**空格隔开各个属性值，不区分顺序**）**

### 布局规则

~~~css
四种布局规则 BFC/IFC/FFC/GFC
浮动塌陷
子元素浮动脱离文档流，父元素高度无法感知子元素高度，父元素高度为0
三个解决办法
---增加clearfix
.parent::after{
  content:"";
  display:block;
  clear:both;
}
---变为BFC
.parent{
  overflow:hidden;
  /*或者  overflow:auto;*/
  /*或者  display:flow-root*/
}

margin布局陷阱
垂直上会合并取最大值，水平上不会
子元素margin-top会穿透父元素
margin:auto，作用在块元素且有宽度，inline无效
flex布局中，margin:auto,会自动变成可以拉伸的弹簧，自动把元素推到两边或中间

如果父元素没有设置 position（relative/absolute/fixed/sticky），子元素的 z-index 是不会生效的。
~~~





标签选择器、类选择器、ID选择器、通配符选择器

复合选择器

- 后代   div span{}
- 子代  div > span{}
- 交集  p.box{}
- 并集 div,p{}
- 伪类    a:
- 超链接伪类    a:link /visited/hover/active
- 伪元素 a::after/before

**继承性**：文字属性和文本属性，父元素设置后子元素会继承，`<a>`标签不会继承父元素字体颜色

**层叠性**：后覆盖前相同属性、不同属性叠加

**优先级**

**css样式冲突**，根据权重进行判断，复杂选择器则根据权重相加比较总和，权重相同，后者生效

`!important>行内样式（1000）>id选择器（100）>类选择器（10）>标签选择器（1）>通配符选择器（0）`

```javascript
p {
  color: red !important;
}
```



**标签的表现形式**

1. 块元素
   - 独占一行
   - 可设置宽高
   - 未设置宽度时，宽度默认父元素100%
2. 行内元素`span label a`
   - 可同行展示
   - 不可设置宽高
   - 宽度由内容撑开
   - 上下padding、上下margin不起作用
3. 行内块元素`input img button`
   - 同行展示
   - 可设置宽高
   - 宽度由内容撑开

转换显示模式：display:block/inline-block/inline

```html
<style>
  a{
    /*转换为块元素；  inline/inline-block*/
    display:block;
    width:400px;
		height:400px;
    color:red;
    background-color:yellowgreen;
    text-align:center;
    line-height:400px;
  }
  
  *{
    /*清楚标签默认样式*/
    padding:0;
    margin:0;
  }
  
  ul{
    /*清楚项目符号*/
    list-style:none;
    list-style-type:none;
  }
  
  /*转换为行内块的问题
  	1，行内块之间的空隙，是由结构里的换行符导致
  	解决方案：
   （1）父元素设置
  		font-size:0;
  	(2)去掉换行符，div全部放一行，或者使用注释进行占位
   （3）设置负边距
  		margin:-40px;
  */
  
</style>
```

### **图文对齐**

主要解决行内块与文字对齐方式，也可以用数值

`vertical-align:middle/bottom/baseline；`

**行内块元素、行内元素水平居中**，针对父元素设置`text-align:center;`

**块元素居中**，直接对块元素设置`margin:0 auto;`

### 常见css属性

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>css常见样式</title>
    <link rel="stylesheet" href="h.css">
    <style>
        /* 类选择器 类名设置可重复，可同时作用，类名最好有实际意义，最常用*/
        .desc {
            width: 200px;
            height: 300px;
            background-color: yellow;
            /* 字体颜色 */
            color: pink;
            font-size: 20px;
            text-align: center;
            /* 行高和高度一致时，文字可以居中 */
            line-height: 300px;

        }
        .detail {
            background-color: antiquewhite;
        }

        /* 伪类选择器 */
        .detail:hover{
            /* 父元素的50% */
            width: 50%;
            /* 4倍字体大小，em当前字体大小 */
            height: 4em;
            background-color: rgb(75, 29, 29);
        }

        /* 标签选择器  作用域太广*/
        div {
            width: 100px;
            height: 100px;
            background-color: brown;
        }
        /* id选择器  缺点id唯一，不符合html文档规范，不常用*/
        #title {
            width: 100px;
            height: 100px;
            background-color: blue;
        }

        /* 字体属性 ，了解 无衬线体、衬线体*/
        .font {
            width:200px;
            height: 200px;
            font-size: 40px;
            /* 粗细 */
            font-weight: bolder;
            font-style: italic;
            /* 可指定多个，没有的话向下溯源 */
            font-family: 'Courier New', Courier, monospace;
            /* font:40px italic bolder "楷体"； */
          	/*文字不换行*/
          	white-space:nowrap;
          	/*指定标签里面的内容超出样式的宽度和高度之后如何处理*/
          	overflow:auto/scroll/hidden;
        }

        .text {
            width: 800px;
            height: 200px;
            /* line-height: 200px; */
            font-size: 20px;
            text-align: center;
            /* 首行缩进 */
            text-indent: 2em;
            /* 下划线 */
            text-decoration: underline;
            /* 字符间间距 */
            letter-spacing: 1px;
            /* 单词间间距 */
            word-spacing: 1px;
          	/*文字超出部分隐藏*/
          	overflow:hidden;
          	/*溢出部分显示省略号*/
          	text-overflow:ellipsis;
        }

        /* 后代选择器 ,有空格    缩小范围*/
        .nav li{
            width: 100px;
            height: 100px;
            background-color: aqua;
        }

        /* 并集选择器 ,逗号隔开*/
        .out,
        p,.inner{
            background-color: yellowgreen;
        }

        /* 交集选择器 */
        .inner.second{
            background-color: pink;
        }

        /* 通配符选择器 ,一般用于初始化界面*/
        * {
            background-color: #f5f5f5;
        }
    </style>
</head>
<body>
    <div class="desc">描述信息</div>
    <div class="desc">描述信息</div>
    <div class="desc detail">描述信息</div>
    <div>我是测试组</div>
    <div id="title">id选择器</div>
    <hr>
    <div class="font">接天莲叶无穷碧，映日荷花别样红</div>
    <hr>
    <div class="text">每天花半小时学习，作一个行业精英每天花半小时学习，作一个行业精英每天花半小时学习，作一个行业精英每天花半小时学习，作一个行业精英每天花半小时学习，作一个行业精英每天花半小时学习，作一个行业精英每天花半小时学习，作一个行业精英每天花半小时学习，作一个行业精英每天花半小时学习，作一个行业精英每天花半小时学习，作一个行业精英每天花半小时学习，作一个行业精英每天花半小时学习，作一个行业精英每天花半小时学习，作一个行业精英每天花半小时学习，作一个行业精英每天花半小时学习，作一个行业精英每天花半小时学习，作一个行业精英每天花半小时学习，作一个行业精英</div>
    <hr>
    <ul class="nav">
        <li class="nav-item">首页</li>
        <li class="nav-item">关于我们</li>
        <li class="nav-item">加入我们</li>
    </ul>
    <hr>
    <div class="out">
        <p>每天学一点</p>
        <div class="inner second">真的就学一点</div>
    </div>

</body>
</html>
```

### 盒子模型

margin 外边距  设置大小，垂直方向会重叠取最大值，水平方向相加

border边框       设置大小、属性，一定要有厚度、样式、颜色

padding 内边距   设置大小

content内容

赋值： 上右下左  、  上/左右/下  、上下/左右  、  全部

盒子大小= content+padding+border

行内元素上下padding、上下margin不起作用

**背景色会填充至padding区域,也会蔓延至边框，不过一般会被边框样式覆盖**

```html
<style>
  div{
    padding-top:20px;
    padding-right:20px;
    border:5px solid dashed pink;
  }
  
</style>
```

**margin嵌套崩塌**：子元素设置的margin-top作用到了父元素身上

1. 给父元素设置`overflow:hidden;`
2. 父元素添加一个极小的padding-top;

**脑子里要有底线、基线、中线、顶线轮廓图**

利用border属性`border-bottom /border-left/right`画出三角形

利用`border-radius：50px/50%;`画圆形



**怪异盒子模型（IE盒子模型）**

 box-sizing

盒子大小不会受padding和border影响，只会挤压content

### 背景属性

`background-color`

`background-image:url();`

平铺`background-repeat：no-repeat;`

`bcckground-position:4px 4px;`背景图片位置距离盒子左边和顶部的像素

`background-attachment:scroll/fixed`背景图片随着盒子滚动/背景图片固定

`background-size:10px 10px/10px auto/cover/contain`背景图片大小宽高，cover填满盒子图片不完整，contain图片完整，但盒子没填充满

**雪碧图**：把所有图片都放一张图片上，减少网络请求次数，使用`background-position`来确认

**透明属性**

`opacity:0-1;`  作用所有元素及内容

`rgba(255,12,11,0.5)` 仅作用颜色

### 文档流

**从左到右，从上往下**

`display :none`从结构中消失，不占据位置，下方元素上移

`display:block`显示

`opactiy:0`消失，依旧占据位置，可触发事件  （常用）

`visibility:hidden/visible`消失，但占据位置，可触发事件

`position: absolute; top: -9999px;`将元素移出视口，仍占空间

### 浮动

1. 浮动：脱离文档流，实现页面布局，专门用于块元素同行展示的问题，空间不够换行，左浮动不会改变布局顺序，右浮动会

 `float:left/right/none`

2. **元素浮动后，会脱离文档流，不占据位置，下方元素上移，**文字不会和浮动元素产生交集，如产生交集，会环绕在浮动元素周围

3. 浮动元素会脱离文档流，因此无法撑起父元素的高度，当父元素没有指定高度时，会塌陷，对布局造成影响
   - 严格指定父元素高度
   - 给父元素添加`overflow:hidden;`,经常使用
   - 在容器所有浮动元素的末尾，追加一个空的元素块，对其设置`clear:both;`

4. 块元素浮动之后，不设置宽度，由内容撑开，一般需指定宽度；行内元素浮动之后，可设置宽高，上下margin也生效
5. 浮动元素同行展示，摆不下时自动换行
6. 使用浮动时，在一个容器里，尽量都使用浮动

### 定位

定位主要用于解决文档流、浮动无法解决的页面布局问题

**正常使用顺序：文档流 > 浮动 > 定位**

定位：把元素定到指定位置

`position:relative/absolute/fixed`三者区别在于参照物不同

`left/right/top/bottom:10px;`释义：元素的左边距离参照物的左边距离10个像素

1. `relative`参照物为自身原本的位置，没有脱离文档流，占据原来位置，一般辅助定位，不常用，一般使用绝对定位。开启定位之后，元素层级得到提升，高于原文档流元素，如果方位未进行设置，则元素在原位
2. `fixed`参照物为浏览器视口，脱离文档流，层级提高，高于文档流元素，网页滚动，不会随着滚动，一般应用”联系我们“
3. `absolute`要先确定参照物，脱离文档流，层级提高，高于文档流元素
   - 参照物为距离自己最近的具备**定位属性的祖先元素**或**html文档**，从自身出发，一层层向上溯源，找不到，以html文档为参照
   - 一般以父元素作为参照物，如果父元素没有定位属性，则添加`relative`,因为`relative`不会影响任何东西

4. `sticky`滚动到一定位置时，不会再随着网页滚动
5. `relative`和`fixed`**块元素**开启之后，不写宽度时，宽度由内容撑开；**行内元素**开启后，可设置宽高

`z-index:999`层级属性，如果父元素也有设置，则无法突破父元素的限制，如果没有，则和外界元素比较；定位元素可以使用此元素，数值大的在最上面展示

### Flex布局

```css
基本概念：水平轴、交叉轴
水平方向
justify-content: center/flex-start/flex-end/space-between(元素之间相等距离)/space-evenly(元素之间与容器之间相等距离)/space-around(元素与容器周围之间保持相等距离)
垂直方向
align-items:center/flex-start/flex-end/baseline(容器基线位置)/stretch(拉伸填满)
注意点：1.当改变列方向时，justify-content控制垂直方向，align-content（align-items）控制水平方向
       2.当改变行列方向后：flex-start/flex-end也调转了

决定行之间的距离
align-content:flex-start/flex-end/center/space-between/space-around/space-evenly/stretch
flex-direction:row/row-reverse/column/column-reverse

flex-wrap:nowrap（挤一行）/wrap(多行)/wrap-reverse
flex-flow:row/column(2选1) wrap/wrap-reverse(2选1)

order：值为±整数，向前后移动

align-self：作用单个元素，同align-items的值


```

### Grid布局

~~~css
diplay:grid;
grid-template-columns: 1fr 1fr 1fr;
grid-template-rows
gap
grid-column
grid-row
grid-template-areas  /*类似画个草图*/
grid-area  /*草图的子元素*/
justify-items  /*控制子元素在容器内水平方向的对齐方式*/
align-items
justify-content   /*控制容器在浏览器内水平方向的对齐方式*/
align-content	    

~~~

### 移动端布局

~~~css
第一种
@media 媒体查询

Flexbox 和 Grid 布局

相对单位如 vw, vh, em, rem, %
  
第二种  视口适配
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  
第三种 响应式图片
<picture>
  <source media="(max-width: 600px)" srcset="image-small.jpg">
  <source media="(min-width: 601px)" srcset="image-large.jpg">
  <img src="image-default.jpg" alt="Responsive Image">
</picture>
  
第四种flex布局
  
第五种百分比布局、单位适配
  
~~~







## H5部分

1. 语义化标签：根据网页布局建立不同的标签，利于SEO优化

   例如：`<header>`、  `<nav>`、`<footer>`

2. 多媒体标签

   ```html
   <body>
   <audio src=“” autoplay controls muted></audio>
   /*多浏览器支持*/
   <audio>
     <source src=""/>
   </audio>
   </body>
   ```

3. input标签type类型添加

   `number 、email、number、color、date、week`

   属性

   `required(必填)/novalidate(关闭表单验证)`

4. 新增元素

   `progress（进度条）/datalist`

5. 引入外部字体

   ```html
   <style>
   @font-face{
   	font-family:"bf";
   	src: url(ziti.ttf);
   }
   p {
   	font-family:"bf";  
   }
   </style>
   ```

6. 字体图标技术，矢量图保证图标清晰

   1. 引入外部字体图标文件
   2. 使用`<i>/<span>`等标签通过类名引入字体图标文件，引用图标
   3. 通过类名选择器选择，通过`font-size、color`等属性设置图标大小

### 

## CSS3部分

1. 取消了私有化前缀，如属性设置不用在强调`-webkit`
2. 新增选择器

- 相邻兄弟选择器： `.classname1+.classname2{}`跟在class1后面的所有class2会被设置样式

- 子元素选择器：`.box>div.inner{}`类名为box底下div类名为inner的样式设置

- 属性选择器：`p[title]{}/p[class^='a'](以a开头)`直接定位

- 伪类选择器

  **超链接伪类**：`link`未被访问、`visited`访问过的状态 、`active`点击瞬间的状态、`hover`悬浮的状态

  `a:active {}`

  **表单伪类**：`focus`、`checked`

  **目标伪类**：跳转到改页面的样式，`target`

  **结构伪类**：`item:nth-child(3/3n)/last-child/first-child`

  **伪元素**：是**行内元素**，给选中的元素添加样式，如第一个字幕颜色；元素中的文本被选中后样式，`after/before/selection`

- 文字阴影

  `text-shadow:水平偏移、垂直偏移、模糊度、阴影颜色；`

- 盒子阴影

  `box-shadow:x y 模糊半径 扩展半径 颜色 `

- 元素过渡

  `transition:0.4s;`

  `transform:rotate(45deg);`控制元素的移动、旋转、缩放、倾斜

  `transform:translate(-50%,50%);`垂直水平居中

- **动画效果多看一些demo学习**，要用的时候再看

## html+css工程demo笔记

工程结构

----css

reset.css

iconfont.css/wtff

工程主项.css

---image

index.html

left:50%用于水平居中，然后元素自身再左移动自身一般的宽度，实现居中

三角形制作，让content宽高为0，边框要有像素，取消一边的像素，然后设置为对称两边的为透明transparent

水平居中，移动端用弹性盒子模型，pc端可是用margin-top平分上下空间    

outline:none

.search~.search- box  波浪号选择器  兄弟选择器，选择后面所有叫search-box的元素

wrap作为公共样式，可作为全局定义，后续子界面可直接继承

浮动影响，父元素高度未知，子元素溢出，使用伪对象 ::after 清除影响

` .play{}`绘制圆角技巧

`.clear::after{content: "";display: block;clear: both;}`  清除浮动影响，作为公共样式

`position:relative;top:10px;`自己小范围移动

`cursor:pointer;`鼠标变小手



# JavaScript

## JS体系

**模块内的属性和函数都是私有的，如果对外使用，需要使用标准语法导出和导入才可以，而这个标准叫 CommonJS 标准**

![image-20250610221443580](/Users/allsun/Desktop/front-end-note/README.assets/image-20250610221443580.png)

![image-20250610221504300](/Users/allsun/Desktop/front-end-note/README.assets/image-20250610221504300.png)

### location对象

```javascript
    // location 对象  
    // 1. href属性 （重点） 得到完整地址，赋值则是跳转到新地址
    console.log(location.href)
    // location.href = 'http://www.itcast.cn'

    // 2. search属性  得到 ? 后面的地址 
    console.log(location.search)  // ?search=笔记本

    // 3. hash属性  得到 # 后面的地址
    console.log(location.hash)

    // 4. reload 方法  刷新页面
    const btn = document.querySelector('.reload')
    btn.addEventListener('click', function () {
      // location.reload() // 页面刷新
      location.reload(true) // 强制页面刷新 ctrl+f5
    })


```

### navigator对象

```javascript
// 检测 userAgent（浏览器信息）
(function () {
  const userAgent = navigator.userAgent
  // 验证是否为Android或iPhone
  const android = userAgent.match(/(Android);?[\s\/]+([\d.]+)?/)
  const iphone = userAgent.match(/(iPhone\sOS)\s([\d_]+)/)
  // 如果是Android或iPhone，则跳转至移动站点
  if (android || iphone) {
    location.href = 'http://m.itcast.cn'
  }})();
```

### history对象

![image-20250610222752200](/Users/allsun/Desktop/front-end-note/README.assets/image-20250610222752200.png)

### localStorage对象、sessionStorage对象

![image-20250610224854227](/Users/allsun/Desktop/front-end-note/README.assets/image-20250610224854227.png)

## 一些重点

隐式转换

arr = []  这个是数组  push   unshift  pop shift  splice  操作原数组 ，map、join、reduce、filter

```javascript
const newArray = oldArray.map(function(element, index, array) {
  // 返回新的元素
});

const numbers = [1, 2, 3, 4];
const sum = numbers.reduce((acc, cur) => acc + cur, 0);

const newArray = arr.filter(function(element, index, array) {
  // 返回 true 或 false，决定是否保留该元素
});

forEach(function(element,index){
  
})
join reverse concat  every  sort  
toFixed()   //保留多少位小数
```

obj = {}  这个是对象

set =()

> 如果函数内部，变量没有声明，直接赋值，也当全局变量看，但是强烈不推荐
>
> 但是有一种情况，函数内部的形参可以看做是局部变量。

#### 断点调试

**作用：**学习时可以帮助更好的理解代码运行，工作时可以更快找到bug

浏览器打开调试界面

1. 按F12打开开发者工具
2. 点到源代码一栏 （ sources ）
3. 选择代码文件

**断点：**在某句代码上加的标记就叫断点，当程序执行到这句有标记的代码时会暂停下来

**块作用域**、 **局部作用域**

**var变量提升、函数提升（不支持表达式提升） 函数的arguments形参对象**

## 常用WebAPIs

querySelector

querySelectorAll

getElementById

getElementByTagName

修改内容

innerText

innerHtml

修改样式

style.color

style.width

style.backgroundColor

修改类名

className   覆盖旧类名

classList.add('classname')   追加类名 remove('classname')  删除  toggle('classname')切换 contains('classname') 是否包含

~~~javascript
自定义属性：

在html5中推出来了专门的data-自定义属性  

在标签上一律以data-开头

在DOM对象上一律以dataset对象方式获取 
<script>
        // 1. 获取元素
        let div = document.querySelector('div')
        // 2. 获取自定义属性值
         console.log(div.dataset.id)
      
</script>
~~~

**间歇函数** setInterval(fn,time)  间隔执行

**延迟函数**setTimeout(fn,time) 隔多久执行，执行一次， clearTimeout(timerId)  返回延迟函数的id

offsetWidth  获取可视宽高、包含元素自身设置的宽高、padding、border

offsetHeight

```javascript
//DOM节点的创建、复制、插入、删除、替换

const p = document.createElement('p')
const p2 = document.querySelector('p').cloneNode(true) //true，该节点下的子节点也全部复制
document.querySelector('.box').appendChild(p2) //在该元素末尾插入

// 第 2 个 li 元素
const relative = document.querySelector('li:nth-child(2)')
document.querySelector('ul').insertBefore(li1, relative) //在父节点中任意子节点之前插入新节点

// 获取 ul 父节点
let ul = document.querySelector('ul')
// 待删除的子节点
let lis = document.querySelectorAll('li')
// 删除节点
ul.removeChild(lis[0])  //使用removeChild一定要有父子关系

const node = document.getElementById('toBeRemoved');
node.remove();

// 父节点
const ul = document.querySelector('ul')
// 所有的子节点
console.log(ul.childNodes)  //childNodes获取全部的子节点，回车换行会被认为是空白文本节点
// 只包含元素子节点
console.log(ul.children) //children只获取元素类型节点

buttons[i].addEventListener('click', function () {
  // console.log(this.parentNode); // 父节点 td
  // console.log(this.parentNode.parentNode); // 爷爷节点 tr
  this.parentNode.parentNode.style.color = 'red'  //parentNode以相对位置查找父节点，
  // 前一个节点
  console.log(this.previousSibling) //previousSibling以相对位置查找前一个节点
  // 下一下节点
  console.log(this.nextSibling)//nextSibling以相对位置查找后一个节点
})  

```

正则表达式

![image-20250610221257703](/Users/allsun/Desktop/front-end-note/README.assets/image-20250610221257703.png)

## 事件

addEventListener('eventname',function(e){})  e为事件对象 ,事件对象常用属性`type、clientX/Y、offsetX/Y、target`

>常用eventname: click /  dbclick / mouseenter /mouseleave  / keydown /keyup /foucs /blur/input
>
>其他常用事件： load(监听所有事件加载完毕) /scroll（滚动条滚动）/resize(窗口大小改变事件)/change（input值被修改，失去焦点后触发）

冒泡：子到父  `addEventListener('eventname',function(e){}，false) `参数为默认为`false`,为冒泡

捕获：父到子  `addEventListener('eventname',function(e){}，true) `参数为`true`为捕获

事件流只会在父子元素具有相同事件类型时才会产生影响

e.stopPropagation

事件委托：给父元素绑定监听事件，使用事件对象的 `e.target === BUTTON`来判断属于哪个类型，再触发回调函数，这样就不用给每个子组件单独添加事件监听了

### 事件循环

> 先执行同步，再执行异步，同步函数按照顺序，异步按照入栈顺序，但是setTimeout函数例外，是按照最短延迟时间

### 异步任务：宏任务、微任务

> 宏任务  setTimeout、setInterval、ajax
>
> 微任务 Promise.then

## 日期对象

```javascript
const date = new Date('2025-01-01')
date.getFullYear()
date.getFullMonth()  //0-11
getHours 获取小时，取值为 0 ~ 23
getMinutes 获取分钟，取值为 0 ~ 59
getSeconds 获取秒，取值为 0 ~ 59
//获取时间戳
date.getTime()
+new Date()
Date.now()
```



## 作用域

一定范围内可以访问到的变量

- 全局作用域  全局变量
- 局部作用域   局部变量   函数作用域、块作用域

函数执行完后，变量被清空

`let`/`const`申明的变量、常量都会产生块作用域，`var`则不会

推荐使用`let`/`const`

函数中未使用任何关键字申明的变量为全局变量

## 垃圾回收机制

全局变量，不回收，关闭页面才回收

局部变量，自动回收

- 引用计数法  ，对象相互引用，导致内存泄漏
- 标记清除法（主流），无法从根部到达的对象被标记回收

## 闭包

闭包是一个特殊函数，可以访问函数作用域中的变量，从代码形式上看闭包是**一个作为返回值的函数**

- 闭包 = 内层函数 + 外层函数的变量
- 封闭数据，实现数据私有，外部也可以访问函数内部变量
- 闭包很有用，允许它将函数与其操作的某些数据（环境）关联起来

问题：

- 可能造成内存泄漏，对闭包的变量引用一直存在

```javascript
function outer(){
	let count = 0;
  function fn(){
    count++;
    console.log(`函数被调用{count}次`)
  }
  return fn;
}
let re = outer();
re();
re();

```

## 箭头函数

```javascript 
let fn = (username) => ({username:username}) //返回一个对象时，要注意括弧
```

无法使用arguments对象，只能使用剩余参数

自己不会创建`this`,只会沿用上一层

箭头函数中的 `this` 始终指向它被定义时的外部作用域中的 `this`

词法作用域是指作用域是在函数定义时确定的，而不是在函数调用时确定的。箭头函数使用词法作用域来解析 `this`，而传统函数使用动态作用域解析 `this`

## 匿名函数

```javascript
let fn = funciton(){
  //dosomething
}
fn()
```

### 立即执行函数

```javascript
(function(){dosomething}()); //注意分号结束
(function(){dosomething})();
```

## 环境对象

函数内部特殊的变量`this`，代表这当前函数运行时所处的环境

谁调用`this`指向谁

## 回调函数

函数A作为函数B的参数，则函数A为回调函数

使用**匿名函数**作为回调函数比较常见

## 递归函数

函数内部自己调用自己，容易发生栈溢出，必需加`return`

## this关键字	

普通函数，谁调用，`this`指向谁，没明确调用对象时，指向`window`对象，严格模式下指向`undefined`

**函数单中才会存在`this`，对象中不存在**

箭头函数不存在`this`，应用最近作用域中的`this`

箭头函数中的 `this` 始终指向它被定义时的外部作用域中的 `this`

词法作用域是指作用域是在函数定义时确定的，而不是在函数调用时确定的。箭头函数使用词法作用域来解析 `this`，而传统函数使用动态作用域解析 `this`

- **箭头函数中的 `this`** 是在定义时确定的，继承自其外部作用域。

- **普通函数中的 `this`** 是在调用时确定的，取决于函数的调用方式。

- 即使使用 `call`、`apply` 或 `bind`，也无法改变箭头函数中的 `this` 绑定。

  call(this,obj,obj)   apply(this,[obj,obj])   bind返回一个新的绑定this的函数

构造函数和原型对象中的`this`都指向实例化的对象

**dom事件的回调函数、prototype的属性方法都不建议使用箭头函数**

```javascript
const btn = document.querySelector('.btn');
btn.addEventListener('click',()=>{
  console.log(this);  //指向window
})

btn.addEventListener('click',funciton(){
  console.log(this);  //指向btn                 
})
```

```javascript
var obj = {
    value: 42,
    method: function() {
        var arrowFunc = () => {
            console.log(this.value);  //this指向obj，arrowFunc无this，找上一层即method方法，method方法在调用时指向obj，因此箭头函数this指向obj
        };
        arrowFunc();
    }
};

obj.method(); // 42

```

## 创建对象

**使用new 的函数，就是构造函数**

### String对象

```javascript
split length substring  includes  toUpperCase   indexOf  replace  match
```

三种方法

```javascript
  const o = {
    name: 'allsun',
    age: 20
  }
```

```javascript
  const o = new Object（{name: 'allsun'}）
```

```javascript
  //使用构造函数，构造函数主要用来初始化对象
  function Pig(name,age){  //默认大写
    this.name: name ，//注意this关键字，this指向的属性 实例对象的属性和方法
    this.age: age    //无需return,自动返回创建的新对象
  }
  Pig.eyes = 2;  //静态成员的属性和方法,一般为公共方法
  Pig.sayHi = function(){//dosomething}
  const peiqi = new Pig('佩奇',3); //只能由 new 关键字来 实例化
```

##   原型对象prototype

构造函数的方法是每个实例对象**独有**的

原型对象的函数是所有实例对象**共享**的

每一个构造函数都有一个`prototype`属性，即**原型对象**，原型对象挂载的方法是**共享**的，不会创建多次，节约内存

构造函数和原型对象中的`this`都指向实例化的对象

### constructor属性

`prototype`中有`constructor`属性指向构造函数

```javascript
//constructor属性应用场景举例
function Person(name) {
  this.name = name;
}
Person.prototype.sayHi = function () {   //只是修改了prototype的一个属性
  console.log("Hi, I'm " + this.name);
};

const p = new Person("小明");
console.log(p.constructor === Person); // ✅ true

function Person(name) {
  this.name = name;
}

// ⚠️ 注意：这里我们整个替换了原型对象！
Person.prototype = {                  //整个prototype被覆盖
  sayHi: function () {
    console.log("Hi, I'm " + this.name);
  }
};

const p = new Person("小明");
console.log(p.constructor === Person); // ❌ false！变成了 Object


Person.prototype = {
  constructor: Person, // ✅ 手动补回来   constructor的作用
  sayHi: function () {
    console.log("Hi, I'm " + this.name);
  }
};
```

## `__proto__`(对象原型)

```javascript
function Person() {}
const p = new Person();

p.__proto__ === Person.prototype;       // ✅ true
Person.prototype.constructor === Person; // ✅ true

```

>p (实例对象)
>│
>└── __proto__ → Person.prototype
>              │
>              └── constructor → Person
>
>原型链就是：对象 → `__proto__` → 原型对象 → 再往上找...

`__proto__用于实例对象指向的原型对象（prototype），__proto__中也有constructor属性，指向创建实例对象的构造函数`

### 原型继承

```javascript
function Person(name,age){
  this.name = name;
  this.age = age;
}

function Man(){}

Man.prototype = new Person()；//必须使用父类的实例化对象
Man.prototype.constructor = Man;
Man.prototype.Swimming = function (){}

const allsun = new Man('allsun',30)
```

### 原型链

基于原型对象的继承使得不同构造函数的原型对象关联在一起，并且这种关联的关系是一种链状的结构，我们将原型对象的链状结构关系称为原型链

**__proto__**对象原型的意义就在于为对象成员查找机制提供一个方向，或者说一条路线

![67679338869](README.assets/1676793388695.png)

## 深浅拷贝

> 浅拷贝只复制一层属性。**如果属性是引用类型（对象、数组），拷贝的是“引用”**，不是实际内容。

```javascript
const obj1 = {
  name: '小明',
  info: { age: 18 }
};

const obj2 = Object.assign({}, obj1); // 或 const obj2 = { ...obj1 }

obj2.name = '小红';          // ✅ 修改不影响 obj1
obj2.info.age = 20;          // ⚠️ 修改 info 影响 obj1！

console.log(obj1.info.age);  // 20 （引用类型共用）

```

> 深拷贝会**递归地复制所有层级**的数据结构，**完全独立**。

1. 通过递归实现深拷贝

   ```javascript
   const obj = {
         uname: 'pink',
         age: 18,
         hobby: ['乒乓球', '足球'],
         family: {
           baby: '小pink'
         }
       }
       const o = {}
       // 拷贝函数
       function deepCopy(newObj, oldObj) {
         debugger
         for (let k in oldObj) {
           // 处理数组的问题  一定先写数组 在写 对象 不能颠倒
           if (oldObj[k] instanceof Array) {
             newObj[k] = []
             //  newObj[k] 接收 []  hobby
             //  oldObj[k]   ['乒乓球', '足球']
             deepCopy(newObj[k], oldObj[k])
           } else if (oldObj[k] instanceof Object) {
             newObj[k] = {}
             deepCopy(newObj[k], oldObj[k])
           }
           else {
             //  k  属性名 uname age    oldObj[k]  属性值  18
             // newObj[k]  === o.uname  给新对象添加属性
             newObj[k] = oldObj[k]
           }
         }
       }
       deepCopy(o, obj) // 函数调用  两个参数 o 新对象  obj 旧对象
       console.log(o)
       o.age = 20
       o.hobby[0] = '篮球'
       o.family.baby = '老pink'
       console.log(obj)
       console.log([1, 23] instanceof Object
   ```

2. lodash/cloneDeep

   ```javascript
   <script src="./lodash.min.js"></script>
     <script>
       const obj = {
         uname: 'pink',
         age: 18,
         hobby: ['乒乓球', '足球'],
         family: {
           baby: '小pink'
         }
       }
       const o = _.cloneDeep(obj)
       console.log(o)
       o.family.baby = '老pink'
       console.log(obj)
     </script>
   ```

3. 通过JSON.stringify()实现，缺点无法复制函数、Map等复杂结构

   ```javascript
   const obj = {
         uname: 'pink',
         age: 18,
         hobby: ['乒乓球', '足球'],
         family: {
           baby: '小pink'
         }
       }
       // 把对象转换为 JSON 字符串
       // console.log(JSON.stringify(obj))
       const o = JSON.parse(JSON.stringify(obj))
       console.log(o)
       o.family.baby = '123'
       console.log(obj)
   ```

   # 防抖节流

   debounce

   ```javascript
   function debounce(fn, delay) {
     let timer = null;
     return function (...args) {
       clearTimeout(timer);
       timer = setTimeout(() => {
         fn.apply(this, args);
       }, delay);
     };
   }
   ```

   throttle

   ```javascript
   function throttle(fn, delay) {
     let lastTime = 0;
     return function (...args) {
       const now = Date.now();
       if (now - lastTime > delay) {
         lastTime = now;
         fn.apply(this, args);
       }
     };
   }
   window.addEventListener('scroll', throttle(() => {
     console.log('滚动中...', Date.now());
   }, 200));
   ```

   

   ![img](README.assets/u=1597464337,4211360165&fm=253&fmt=auto&app=138&f=JPEG.jpeg)

# AJAX和Axios

> 使用XMLHttpRequest对象与服务器进行通信

## **使用原生XHR发起ajax请求**

```javascript
const xhr = new XMLHttpRequest()
//使用XHR携带查询参数，可以使用模板字符串，进行动态传参
xhr.open('请求方法', '请求url网址？参数=孙哈哈')
xhr.addEventListener('loadend', () => {
  // 响应结果
  const data = JSON.parse(xhr.response)
  console.log(xhr.response)
})
xhr.send()
//URLSearchParams对象，格式化查询参数
// 1. 创建 URLSearchParams 对象
const paramsObj = new URLSearchParams({
  参数名1: 值1,
  参数名2: 值2
})

// 2. 生成指定格式查询参数字符串，仅仅做格式转换，然后需要拼接在url上
const queryString = paramsObj.toString()
// 结果：参数名1=值1&参数名2=值2

// 1. 告诉服务器，我传递的内容类型，是 JSON 字符串
xhr.setRequestHeader('Content-Type', 'application/json')
// 2. 准备数据并转成 JSON 字符串
const user = { username: 'itheima007', password: '7654321' }
const userStr = JSON.stringify(user)
// 3. 发送请求体数据
xhr.send(userStr)
```

## **Promise对象**

> 解决回调函数地狱问题：为了处理一系列异步操作，一个回调函数嵌套另一个回调函数，导致代码层层嵌套、可读性差、难以维护的现象,或者使用async/await解决，await原地等待函数返回结果

地狱demo:

```javascript
getUser(userId, function(user) {
  getOrders(user.id, function(orders) {
    getOrderDetails(orders[0].id, function(details) {
      sendEmail(user.email, details, function(result) {
        console.log('Done!');
      });
    });
  });
});

```

> Promise使用链式调用解决

```javascript
//1. new Promise 对象执行异步任务。2. 用 resolve 关联 then 的回调函数传递成功结果。3.用 reject 关联 catch 的回调函数传递失败结果。
//使用axios或者fetch函数直接可以使用then链式调用，本身返回的就是一个Promise对象
/**
 * 目标：使用Promise管理XHR请求省份列表
 *  1. 创建Promise对象
 *  2. 执行XHR异步代码，获取省份列表
 *  3. 关联成功或失败函数，做后续处理
*/
// 1. 创建Promise对象
const p = new Promise((resolve, reject) => {
  // 2. 执行XHR异步代码，获取省份列表
  const xhr = new XMLHttpRequest()
  xhr.open('GET', 'http://hmajax.itheima.net/api/province')
  xhr.addEventListener('loadend', () => {
    // xhr如何判断响应成功还是失败的？
    // 2xx开头的都是成功响应状态码
    if (xhr.status >= 200 && xhr.status < 300) {
      //关联成功函数
      resolve(JSON.parse(xhr.response))
    } else {
      //关联失败函数
      reject(new Error(xhr.response))
    }
  })
  xhr.send()
})

// 3. 关联成功或失败函数，做后续处理
p.then(result => {
  console.log(result)
  document.querySelector('.my-p').innerHTML = result.list.join('<br>')
}).catch(error => {
  // 错误对象要用console.dir详细打印
  console.dir(error)
  // 服务器返回错误提示消息，插入到p标签显示
  document.querySelector('.my-p').innerHTML = error.message
})
```

### Promise对象的三个状态：pending/fulfilled/reject

![image-20250616231753832](/Users/allsun/Desktop/front-end-note/README.assets/image-20250616231753832.png)

## Promise.all

> 打包所有Promise对象，有一个失败就抛出异常

```javascript
const p = Promise.all([Promise对象, Promise对象, ...])
p.then(result => {
  // result 结果: [Promise对象成功结果, Promise对象成功结果, ...]
}).catch(error => {
  // 第一个失败的 Promise 对象，抛出的异常对象
})
```



## **axios语法，封装了XHR对象**

```javascript
//常用http请求方法，get/post/delete/patch/put
axios({
  url: '目标资源地址',
  params: {
    参数名: 值
  },
  method:'', //默认get
  data:{
    参数名：值  //如username
  }
}).then((result) => {
  // 对服务器返回的数据做后续处理
}).catch((error) => {
  //处理失败         
})
```

## 图片上传

> 先用文件选择元素，获取到文件对象，然后装入 FormData 表单对象中，再发给服务器，得到图片在服务器的 URL 网址，再通过 img 标签加载图片显示



# NodeJS

模块化，一个文件夹就一个模块，一个模块中需要有package.json文件，package.json文件记录说明信息，及导入时，默认的导入文件，一般为index.js

commonJS    export.module={}     require

# webpack

> 安装至全局软件包，静态模块打包工具，是分开打包的，需要针对js代码、html、css分别做打包设置，打包方式通过入口构建依赖图

## 打包JS代码

```javascript
//1、项目根目录，新建 Webpack.config.js 配置文件
const path = require('path')

module.exports = {
  entry: path.resolve(__dirname, 'src/login/index.js'),
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: './login/index.js'  
  }
}
```

## 打包html

```javascript
//安装html-webpack-plugin插件，建议只在生产环境中压缩
const HtmlWebpackPlugin = require('html-webpack-plugin')

module.exports = {
  // ...其他 webpack 配置
  plugins: [
    new HtmlWebpackPlugin({
      template: './src/index.html', // 模板路径
      minify: {
        removeComments: true,             // 删除注释
        collapseWhitespace: true,         // 删除空格
        removeRedundantAttributes: true,  // 删除多余属性
        useShortDoctype: true,
        removeEmptyAttributes: true,
        removeStyleLinkTypeAttributes: true,
        minifyJS: true,                   // 压缩页面中的 JS
        minifyCSS: true,                  // 压缩页面中的 CSS
        minifyURLs: true
      }
    })
  ]，
  module: { // 加载器
    rules: [ // 规则列表
      {
        test: /\.css$/i, // 匹配 .css 结尾的文件
        use: ['style-loader', 'css-loader'], // 使用从后到前的加载器来解析 css 代码和插入到 DOM
      }
    ]
  }
}

```

## 打包CSS

>Webpack 默认只识别 JS 和 JSON 文件内容，所以想要让 Webpack 识别更多不同内容，需要使用加载器

介绍需要的 2 个加载器来辅助 Webpack 才能打包 css 代码

* [加载器 css-loader](https://webpack.docschina.org/loaders/css-loader/)：解析 css 代码
* [加载器 style-loader](https://webpack.docschina.org/loaders/style-loader/)：把解析后的 css 代码插入到 DOM（style 标签之间）



# Vue2学习·

## 本次常见JS方法整理

~~~javascript
list.reduce((sum,item) => sum += item.num,0)
arr.filter(item => item.id !== id)
slice()
+Date.now()可作为新增id值
toFixed(2)  保留2位小数
list.map((item) => {name:item.name,value:item.price})
join('、')
this.$router.push(`/search?key=${this.inputValue}`)
axios.get/set/delete

~~~

## Vue2语法

### 指令、指令修饰符

~~~javascript
v-if  删除dom结构
v-show  仅针对css，display:none 做控制
v-for中的 ：key属性  对删除的影响，所谓的原地删除
:src=''
:class="{pink:true,red:false}"
:class="[pink,red]"
:style="{color:'red',backgroundColor:'green'}"
v-model原理，value属性和input事件的合写  :value="msg"  @input="msg = $event.target.value"  获取事件对象的形参

//指令修饰符
v-model.trim
v-model.number
@click.stop
@click.prevent  阻止默认行为
~~~

#### 自定义指令

~~~javascript
自定义指令：封装一些dom操作,指令的值通过binding.value传递
全局注册 
Vue.directive('指令名'，{
  "inserted"(el){
    //el指令所绑定的元素
    el.focus()
  }
})
局部注册
directives:{
  "指令名":{
    //插入dom，执行自动获取焦点
    inserted(el){
      el.focus()
    }
    //更新时触发
    update(el,binding){
      el.style.color = binding.value
    }
  }
}
调用  <input v-指令名 type>  当前元素被插入到页面中时，调用函数
应用场景：v-loading  页面加载的时候显示加载图标，使用伪类添加蒙层

~~~

#### v-model的语法糖

~~~javascript
例如在 input输入框上，是value属性和input属性的合写，提供数据双向绑定
<input v-model="msg" type="text">
<input :value:"msg" @input="msg = $event.target.value" type="text">

表单类组件封装（注意是组件，非input等标签）v-model无法使用props父传子的属性进行绑定，因此要使用$emit进行更新，需要将v-model拆解使用  
父组件  @input="selectId = $event"  子组件 props属性名应为value $emit事件名应为 input ,父组件才能直接使用v-model
~~~

![image-20250306172726091](README.assets/image-20250306172726091.png)

![image-20250306172628823](README.assets/image-20250306172628823.png)

### Vue实例属性

#### data/computed/methods/watch

```javascript
data属性
computed 和method的区别，computed可以缓存结果，如果依赖项值变化了，会自动重新计算
完整写法，默认只提供 get() ，需自定义 set(value),提供了set方法，才能够修改computed中的属性值
不需要在 methods 里手动调用 computed 的 set 方法，因为 Vue 会在你修改计算属性时自动触发 set
data() {
    return {
      firstName: "John",
      lastName: "Doe"
    };
  },
  computed: {
    fullName: {
      get() {
        return this.firstName + " " + this.lastName;
      },
      set(newValue) {
        const names = newValue.split(" ");
        this.firstName = names[0];
        this.lastName = names[1] || "";
      }
    }
  }

理解data属性和计算属性，计算属性是基于data属性加工而来，都是一个值
computed 属性是基于 data 属性或者 props 来计算值的，但它也可以基于其他计算得到的值，或者基于外部的数据
例如
computed: {
    // 获取地址栏的搜索关键字，直接变为一个属性，在后面的方法中可以使用this调用
    querySearch () {
      return this.$route.query.search
    }
  }

watch 简单写法，可以监听data、computed/vue组件的props变化
完整写法
deep:true,   深度监听数组及对象内部属性
-------
immediate:true,//一进页面立刻执行一次
handler(){
  //立即执行函数
}





querySelector()  查找的是整个页面
ref=属性名 ，渲染完成之后 使用this.$ref.ref属性名 查找的是当前组件，除了获取dom 也可以获取 组件实例，调用组件的方法  this.$ref.baseForm.resetValue()

vue是异步dom更新队列，使用$nextTick，等dom更新完，才会触发才此方法里的函数体

```



#### 生命周期函数

```javascript
vue的生命周期（共8个钩子函数）
beforeCreate 实例创建，data/methods都未初始化，不能访问data等属性
created data/methods初始化完成，可访问，但未挂载到dom节点，适合初始化数据
beforeMount 模板编译完成，虚拟dom创建完成
mounted 挂载到dom节点，可以操作dom---应用场景，一进界面，获取焦点     常用
beforeUpdate 数据修改，视图未更新，期间可以添加逻辑处理
Updated 数据修改，视图已更新
beforeDestroy data等属性可以访问，释放vue以外的资源（清除定时器、延时器）  常用
destroyed 组件注销，this.el仍然可以访问，但不具备响应式

模板当中可以省略this，在created函数当中需使用  this.$route.query.参数名


vue的生命周期仅针对挂载的dom节点，vue实例优先创建于被挂载的dom，其余dom优先加载
```

### 组件

~~~javascript
components组件注册
组件的概念，main.js是入口，导入vue、APP.vue根组件，渲染加载然后挂载到dom节点
结构 App.vue中template只能有一个div根元素
样式 scoped,作用于当前组件，原理，所有dom结构都加上了 ‘data-v-哈希值’，css选择默认添加
逻辑  data必需是函数，保证每个组件实例创建的数据都是独立的


普通组件：
局部注册,只能在注册内的组件内使用 components:{组件名:组件对象}
全局注册，所有组件内都能使用，在main.js中注册  Vue.component(组件名，组件对象)
const app = createApp(App);

// 全局注册组件
app.component('ChildComponent', ChildComponent);

异步组件
用于懒加载

~~~

#### 组件通信

~~~javascript
组件通信
父子关系 父组件通过props传递数据、子组件通过$emit更新、props校验（type、require、default、validator()）、单向数据流

非父子关系 
第一种provide & inject---简单类型 非响应式，复杂类型  响应式
//数据源
provide() {
    return {
      globalMessage: "Hello from Provide!" // 提供数据
    };
  }
//数据接收
inject: ["globalMessage"] // 注入祖先组件提供的数据
第二种 eventbus(vue2)   mitt(vue3)
非父子关系  event bus 1.创建一个空的eventbus vue实例；2.A监听event bus 实例的事件 Bus.$on(eventName,回调函数)；3.B组件触发 Bus.$emit(eventName,'')
beforeDestroy() {
    Bus.$off("custom-event"); // 避免内存泄漏
  }

跨层级（孙子）：爷爷provide，将data中的属性共享  孙子inject---简单类型 非响应式，复杂类型  响应式

.sync修饰符  实现父子组件的数据双向绑定，可自定义属性名 :visible.sync="isShow"  等于  :visible="isShow" @update:visible="isShow = $event" / 子组件 this.emit('update:visible',false)

兜底方案  vuex(vue2)    pina(vue3)
~~~

#### Vuex

~~~javascript
vuex:管理vue多组件共享的数据，多个组件共同维护一份数据，响应式变化，单向数据流，组件中不能直接修改
store/index.js专门存放vuex
Vue.use(Vuex)
new Vuex.Store()
挂载到main.js中，和router挂载类似
this.$store
const store = new Vuex.Store({
  strict: true, //严格模式，单向数据流
  state:{
    '共享变量名': 变量值
    list:[1,2,3,4,5,6,7,8,9,10]
  }
  mutations:{
    //第一个参数固定为state,n称作为payload载荷
    addCount(state，n){
      state.count += 1
    }
  }
})
访问
<template>{{$store.state.xxx}}</template>
在vue文件中，export default里<组件逻辑里>this.$store.state.xxx</组件>
在js文件中，<script>store.state.xxx</script>
mapState 将state数据自动映射到组件的计算属性中（computed）
compute:{
  ...mapState(['count'])
}
修改  只有mutations修改state的值。单向数据流,必需是同步的，便于监测数据变化，记录调试

在组件中调用 this.$store.commit('addCount',参数)，参数只能为1个，如有多个参数，考虑传对象或数组
mapMutations将mutations方法自动映射到组件的methods中
methods:{
  //页面中可直接使用addCount
  ...mapMutations(['addCount'，'subCount'])   
}

actions 支持异步，不能直接操作state，操作state,还是需要commit mutations
actions:{
  //此处没分模块，context可以理解为store
  setAsyncCount(context,num){
    setTimeout(() => {
      //changeCount就是mutations里的方法
      context.commit('changeCount',num)
    },1000)
  }
}
组件methods中调用
this.$store.dispatch('setAsyncCount',200)
mapActions,将actions中的方法映射到组件的methods中
methods:{
  //页面中可直接使用addCount
  ...mapActions(['setAsyncCount'])   
}
this.setAsyncCount(666)

getters，类似computed属性，基于state做的各种运算，依赖state的变化
getters:{
  //第一个形参是state,必须有返回值,第二个参数可以是getters，访问内部的getters
  filterList(state){
    return state.list.filter(item => item > 5)
  }
}

{{$store.getters.filterList}}
computed:{
  ...mapGetters(['filterList'])
}
映射完，直接直接使用{{filterList}}

module模块，vuex使用单一状态树，每个模块都有自己的state,mutations,actions,getters
user.js
const state = {
  userInfo:{
    name: 'sun',
    age: 32
  },
  score: 99
}
const mutations = {}
const actions = {}
const getters = {}
export default{
  namespaced: true,  ---命名空间
  state,
  mutations,
  actions,
  getters
}
--------------
const store = new Vuex.Store({
  modules:{
    user
  }
})
访问
$store.state.模块名.xxx
mapSate('模块名',['xxx'])  --需要开启命名空间,不加的话默认挂载到全局，加的话挂载到子模块
$store.getters['模块名/xxx']
mapGetters('模块名',['xxx'])
$store.commit('模块名/xxx'，额外参数)
mapMutations('模块名',['xxx'])
$store.dispatch('模块名/xxx'，额外参数)
mapActions('模块名',['xxx'])
~~~



#### 插槽

~~~javascript
插槽：组件内部结构的自定义；后备内容（默认值）
<slot>这句话是默认内容</slot>  占位封装
默认插槽：只能定制一个位置
具名插槽：多个slot ,使用name属性区分
<slot name='head'>
<slot name="content">
使用
<template v-slot:head>或者<template #head>
大标题
</template>
作用域插槽（传参）,添加属性传值,本质上给插槽绑定数据，供组件使用
<slot :row="item" msg="测试文本"></slot>
调用传参
<template #default="obj">
  <button @click="del(obj.row.id)"></button>  
</template>
~~~

## Vue路由

~~~javascript
单页应用程序（SPA）点击导航不重新加载跳转  SEO差，页面按需更新
多页：点击导航会重新加载跳转              SEO优

路由：访问路径和组件的对应关系，步骤5+2  router-view
router-link 提供高亮类名： router-link-extra-active/router-link-active(模糊匹配，用的多)，可以给这两个类名配置别名

路由404、重定向
const route = new VueRouter({
  routes:[
    { path: '/',redirect: '/home'}
    { name:'路由名', path: '/home',component: Home}
    { path: '*',component: NotFound}
  ],
   linkActiveClass: "my-active", // 修改 router-link-active 的名称
  linkExactActiveClass: "my-exact-active"， // 修改 router-link-exact-active 的名称
  mode:"history" //hash
})

<router-link to='/my'>

声明式导航 跳转传参
1、查询参数传参
路径传递  'to=/path?参数名1=值&参数名2=值'    接收  $route.query.参数名  适合多个参数
2.动态路由传参  参数可选符'?',表示该参数非必填
配置路由 path:'/search/:words'  配置导航 to='/path/参数值'  接收 $route.params.参数名  适合传单个参数
编程式导航（js跳转）
1.path路径跳转 路由传参
this.$router.push('/路径/参数名1=参数值1？参数名2=参数值2')
this.$router.push({
  path:'路径'，
  query: {
    参数名: '参数值'
  }
})
this.$router.push('/路径/参数值')
this.$router.push({
  path:'路径/参数值'
})

2.name命名路由跳转（适合path路径长的场景）
this.$router.push({
  name: '路由名',
  query: {
    参数名:'参数值'
  }
})
this.$router.push({
  name: '路由名',
  params: {
    参数名:'参数值'
  }
})

路由模式
hash（默认，地址带'#'号）
history(常用，需服务器端支持,后台配置访问规则)
~~~

## 项目如何运行

~~~shell
npm install
如出现报错，请先解决版本依赖问题
npm run serve
运行项目
~~~



# Vue3学习

相比Vue2编程式API、响应式数据(proxy)、

## setup语法糖

~~~javascript
<script setup> //可以不用return返回变量和函数了，作用在beforeCreate()函数前，this指向undefine
	
</script>
~~~



## reactive/ref

~~~javascript
reactive 支持复杂对象
ref 简单数据类型、复杂对象

ref在script中，需要使用'.value'访问值
~~~



## watch/computed

~~~javascript
computed中也需要用get/set才能修改值
watch([ref1,ref2],([1now,2now],[1old,2old]))
~~~



## defineOptions()

~~~javascript
避免setup占据了script的选项配置，除了props/emits/expose/slots除外
<script setup>
	defineOptions({
  	name:'sun'
  	//自定义更多属性
})
</script>
~~~

## 父子通信

~~~javascript
defineProps
~~~



## 模板引用

~~~javascript
通过ref获取dom对象或者组件，在setup语法糖下，组件内部的数据和方法是不对外开放的，可以通过defineExpose()指定哪些属性和方法允许访问
~~~

## provie/inject

~~~java
可以跨层级传递数据和方法，实现通信
  父组件 provide  提供了数据，父组件也要提供修改的方法，谁的数据谁维护原则  
  子组件inject
  
  传普通数据 provide('参数名'，'参数值')
  传响应数据 provide('参数名'，ref对象)
  传函数
~~~



## defineModel()

~~~javascript
defineProps   defineEmits()
~~~





## pinia状态管理工具

~~~javascript
支持组合式API
由vuex的5个（state   actions  getters  mutions module）变成了3个 state   actions  getters

定义store

actions 异步实现  async

直接解构会丢失响应性，使用关键字 sotreToRefs()，方法直接解构就可以

pinia持久化插件
psersist  key  局部持久化
~~~



# Vue工程化

~~~javascript
vue的工程化，源代码->自动化编译压缩组合->运行的代码
自动化编译环节设计到不同的配置项，去将less、ts代码转化为浏览器运行的代码
'@/' 等价于 ‘src/’从根目录开始寻找
babel 语法降级
jsconfig.json 配置js语法提示
vetur vscode语法高亮插件
less css的语法糖
less-loader
VueRouter vue2 vuerouter3 vuex3 /344
eslint 代码规范 无分号规范

vscode-配置-设置-trigger on tab   
查看已安装的包 npm list
组件库 按需导入（推荐）/全部导入
pc端  element-ui  ant-design-vue
移动端 vant-ui 更新快/Mint UI/ Cube UI
业务逻辑，CRUD之后都要重新渲染
npm install -D  记录到devDependencies ,开发环境

1. 安装vant2，结果npm ERR! While resolving: @vue/eslint-config-standard@6.1.0
   npm ERR! Found: eslint-plugin-vue@8.7.1
   **解决方案：npm uninstall @vue/eslint-config-standard**

   npm install @vue/eslint-config-standard@6.1.0

2. 学会解决路径依赖，package-lock.json文件开发中锁定依赖

   npm -D 开发依赖，可以记录到package.json文件中

3. 按需加载控件   npm i babel-plugin-import -D

4. 学会看eslint的报错进行格式整理

5. npm i postcss-px-to-viewport@1.1.1 -D

先配置路由，再做页面，单个页面独立展示的都为一级路由，

安装 axios   npm install axios

验证码base64格式，解析到页面中，使用v-binding
vuex刷新后会丢失
防抖，执行一个动作后一段时间才能再执行
节流，一段时间内只能执行一次动作
谷歌浏览器 调试工具 network-no throttling -slow 3G 网速慢的情况

请求拦截器中，添加loading
响应拦截器中，关闭loading

全局前置守卫，需要登录才可以访问的界面，提示跳转到登录界面

开发一般步骤：静态结构、假数据、接口、接口数据请求打印看结构、渲染

route.replace和push的区别，push会叠加历史记录

动态类 :class={disabled: selecout === 0}

<!-- 既希望保留原本的形参，又需要通过调用函数传参 => 箭头函数包装一层 -->
<CountBox @input="(value) => changeCount(value, item.goods_id, item.goods_sku_id)" :value="item.goods_num"></CountBox>

mixins混入概念，对组件公用方法的抽象，可以应用到任何组件中

路由懒加载，被访问才加载组件


npm ->  yarn -> pnpm  更快更省空间
eslint 看规范
prettier 美化

使用脚手架创建项目后，需要安装依赖再启动项目

husky
~~~


 **标签相关：**

- clientWidth\clientHeight   标签内容+内边距的宽高（不包含滚动条，要减去滚动条）
- offsetWidth\offsetHeight   标签内容+内边距+边框的宽高
- scrollWidth\scroHeight        滚动高度，放不下的内容也算进去
- clientLeft\clientTop             左边框的宽、上边框的宽
- scrollLeft\scrollTop              水平方向的滚动距离、竖直方向的滚动距离   
  
  - 设置滚动距离 scrollLeft\scrollTop  = 100  
  
    
  
    

 *标签边框的外边界与已定位上层标签的边框的内边界的距离（上层标签没有定位，就时到body的内边界的距离*

 **尺寸****、位置**

- innerWidth\innerHeight   窗口可视区域的宽、高

- outerWidth\outerHeight   窗口的宽高

- screenLeft—screenX  \   screenTop—screenY    窗口的左边界、上边界 与电脑显示屏左边、上边的距离

- scrollBy();  调动一次滚动多少（增量）；para1：x方向的增量     para2：y方向的增量

- scrollTo();   滚动到（终值）  ;    para1：x方向的值  ;   para2：y方向的值

  - 例:  `window.scrollTo({`
           `left:0,`
    		           `top:0,`
                `behavior:"smooth"`   
      
      ​      `})`
      
      left:x方向的值：top：y方向的值
      
      ​      // behavior:行为；smooth：平滑；
      
      ​      // behavior:类型String，表示滚动行为，支持参数 smooth（平滑滚动），instant（瞬间滚动），默认值 outo，实测效果等同于 instant；
      
      

###### **坐标**（屏幕左上角为坐标原点）

- event.screenX    \     event.screenY     与屏幕左边界、上边界的距离
- event.pageX     、event.pageY     与 页面左边界、上边界的距离
- event.clientX   \     event.clientY      与可视区域左边界、上边界的距离
- event.offsetX    \   event.offsetY      与所在标签左边界、上边界的距离
- event.X   \   event.Y  
- event.layerX    \    event.layerY



###### **导航器**

​	navigator :导航。获取用户代理（设备、浏览器、操作系统的相关信息）

​	// 浏览器存储：

- ​    // localStorage :本地存储 ;存储容量在5M左右；持久化存储（不删除就一直在）。

- ​    // sessionStorage ：会话存储；存、取、删方法与localStorage一致；存储容量在5M左右；浏览器窗口关闭数据消失。

- ​    // cookie ：document.cookie属性用于存取；存储容量在4k左右；存储有效期，默认是会话；也可以设置有效期。

- setItem:以key-value形式存储数据；只能存储基本类型；取出一律是字符串；

-  // 存储对象：将对象转化为字符串，然后进行存储

  ​    `var goods = { title: "风衣", price: 1000 };`

  ​    `var goodsStr = JSON.stringify(goods);`

  ​    `localStorage.setItem("goods", goodsStr);`

- getItem:根据key取出value；取出一律是字符串

  ​    `var account = localStorage.getItem("account");`

  ​    `var password = localStorage.getItem("password");`

  ​    `var age = localStorage.getItem("age");`

  ​    `var sex = localStorage.getItem("sex");`

- 取出的对象字符串，可以通过json的parse方法转化为对象

  ​    `var goodsStr = localStorage.getItem("goods")`

  ​    `var goods = JSON.parse(goodsStr)`

  ​    `console.log(account);`

  ​    `console.log(password);`

  ​    `console.log(sex);`

- removeItem:根据key，删除key-value

  ​    `localStorage.removeItem("sex")`



###### **历史记录**

history:浏览器的历史记录，基于历史记录，可以去上一页或者去下一页..

back:返回,基于历史记录，历史记录有上一页，才能返回

 forward:前进                 forward:前进

go:去 ，前进或后退  para1:正数是前进，负数是后退；n就是前进\后退n层



###### **浏览器端定位**

- 获取地理位置

  `console.log(window.navigator.geolocation);`

- 获取挡墙位置

  ​    para1 :获取位置成功时回调函数

  ​    para2:获取位置失败时回调函数

  ​    第一个function：获取成功的方法参数

  ​    第二个function: 获取失败的方法参数

  `navigator.geolocation.getCurrentPosition(function(data){`

  ​      `console.log(data);`

  ​      `console.log(data.coords.altitude);`

  ​      `console.log(data.coords.longitude);`

  `},function (error) {`

  ​      `console.log(error);`

  `})`

###### **同步**

 同步: synchronize;代码按照顺序执行,阻塞的;

 异步: asynchronize;代码不按照顺序执行,非阻塞的.(同步执行结束,才会执行异步)

​			常见的异步操作

​     		1) 事件操作

​    		 2) setTimeout\setInterval

   		  3) ajax





###### **正则表达式**

​	js中一个新的类型，RegExp,regular expression ；按照特定语法书写一个表达式，可以用于检测字符串是否满足要求。

*常用正则表达式：手机号、邮箱、身份证、密码、账号、电话号码*；

​	 正则表达式 语法：

​     ^ ： 以xxxx开头

​     $ : 以xxx结尾

​     ^ $: 一起写，代表字符串只有它们中间的内容

​     \b : 匹配单词边界  例：var reg1 = /\bis/

​     \d : 匹配数字 字符串中是否有数字，不管有几个哪个数字

​     \w : 匹配字符、数字、下划线

​     \s : 匹配空格

​     . : 匹配除了换行符以外任意字符

​     [abc] : 字符组，匹配字符组中任意一个字符;[a-z];[A-Z];[0-9];a到z，0到9;



​     \W : 是\w 的反义词；匹配不是字母、数字、下划线

​     \D : 是\d 的反义词，匹配不是数字

​     \S : 是\s 的反义词，匹配不是空格 

​     \B : 是\b 的反义词，匹配不是单词边界

[^abc]: 字符组反义词，匹配不是a,b,c





​     + : 匹配前导字符1次或者多次

​     * : 匹配前导字符>=0 次

​     {m,n}: 匹配前导字符至少m次，至多n次  例：/^a{2,5}$/ a至少2次，至多5次

​     {m} : 匹配前导字符m次

​     {m,} :匹配前导字符最少m次



​     x | y :匹配x或者y



​     ?:patten: 匹配pattern

​     /^industr(?:y|ies)$/

​     var reg2 = /^industr(?:y|ies)$/

​     var result = reg2.test("industry")

​     console.log(result);



​		*测试*      

* ​	test:测试；  para1：待检验的字符串    返回值：boolean类型；true:说明字符串满足要求；反之，false*



###### **BOM**	

​	*browser object moddl ; 浏览器对象模型；封装了与浏览器相关的操作，比如:地址栏地址操作、前进、后退；浏览器存储....*

location:位置

​    ./  当前文件夹    ../  别的文件夹

------





#### **jQuery**

 jquery:是js脚本库；包含了一系列的API，例如 标签的遍历、属性样式操作，标签的内容操作、标签的事件操作、标签的动画操作，ajax

​     简单、功能丰富、尺寸大小、浏览器兼容器好；

​     API：application programming interface ,应用程序编程接口。

​     jquery,2006年开源项目;目前最新版是 3.5.x



​     jquery使用步骤

- ​     1）下载并引入
- ​     2）会提供一个全局变量，名字是 $(或者jQuery);
- ​     3）



​     标签查询

​     	para1：选择器

​     	返回值：找到的标签构成的类数组对象，称为jQuery对象。



​     jQuery新增选择器

- ​     :gt(n):索引大于n
- ​     :lt(n):索引小于n
- ​     :eq(n):索引等于1
- ​     :odd ：索引为奇数
- ​     :even: 索引为偶数



*each方法*: 进行jQuery 对象的遍历；类似数组的forEach方法；

​			例：eles.each(function (index, ele) {

​      						console.log(index);

​     						 console.log(ele);

​    					})

 // 标签内容；

​     jQuery 支持批量操作；参数非常灵活；

​     html方法

​     赋值：将查找的jquery对象中所有的标签html都修改了;

​     eles.html("hello world");



​     对于jquery对象中每一个标签，这个回调函数都会执行一次；回调函数的返回值就是对应标签的HTML内容。

​     回调函数的参数：para1：遍历时的索引，para2：旧的html； 返回：新html

​	取值：取的是jquery对象中第一个标签的html的值

​	text();用法同html() ;作业赋值\取值标签内的文本。

​	val():用法同html():作用赋值\取值input标签的内容。



###### **标签时间操作**

事件监听的通用方法 on：   para1：事件名;   para2:事件的回调函数;

> $("ul>li").on("click", function (event) {
>
> ​      console.log("li click");
>
> ​      console.log(event);
>
> ​      console.log(this);
>
> ​       <!--index 方法的作用是获取被点击标签this的索引-->
>
> ​       <!--$(this)：将标签对象转化为jquery对象。-->
>
> ​      var index = $(this).index();
>
> ​      console.log(index);
>
> ​    })

*简写*

jquery中封装了一系列以事件名称为方法名的函数；可以直接使用。例如：

> ​     $("ul>li").click(function () { })
>
> ​     $("ul>li").mouseover(function () { })



hover：悬浮；实际是移入、移出两个事件

> ​    $("ul>li").hover(function () {
>
> ​      console.log("移入");
>
> ​    }, function () {
>
> ​      console.log("移出");
>
> ​    })



​     *移除事件监听*

> ​     off方法无参数，是移除所有事件监听
>
> ​     para1：事件名称：移除该名称对应的事件监听。
>
> ​     $("ul>li").off("click")

*事件代理*

> ​    `para1:事件名  	para2：选择器		para3：回调函数`

 `$("ul>li").on("click", "li:nth-child(3)",`

​      `function () {`

​        `console.log("click hhhhh");`

​        `console.log(this);`

​      `})`



*自己通过代码触发事件*

> ​     trigger:触发器

​    `$("ul>li").trigger("click")`

one:一次性事件触发

​	 `$("ul>li").one("click", function () {`

​      `console.log("one click");`

​    `})`

$(document).ready()



###### 标签的css样式操作——`**取值、赋值**`

*赋值*：para1：修改的属性 	para2：function函数            function：para1：索引	para2：旧值

`$("ul>li").css("color", "red")`

​    `$("ul>li").css({`

​      `color: "blue",`

​      `backgroundColor: "red"`

​    `})`

取值—（取第一个css）

`var result = $("ul>li").css("font-size");`

​    `console.log(result);`



###### **属性操作**

*赋值*

 `$("p").attr("title", "哈哈哈");`

​    `$("p").attr({`

​      `class: "red",`

​      `title: "呵呵呵"`

​    `})`

​    `$("p").attr("id", function (index, oldValue) {`

​      `return "p-" + index;`

​    `})`

*取值*       	`$("p").attr("id")`



*prop:property属性；通常用他操作boolean类型的属性*

`$("input:nth-child(3)").prop("checked");`

*删除属性*

​	`$("p").removeAttr("title");`

*class属性*

- ​	`$("P").addClass("big") //添加`
- ​    `$("P").removeClass("red") //删除`
- ​    `$("p").toggleClass("big") // 切换class，有属性就删除，无属性就添加`

*通过data 方法向标签对象上存取数据*

 	`$("p").data("index", 100);`

​    `var index = $("p").data("index")`



###### **文档处理**

*添加子标签（内部操作)*       `var ul = $("ul");`

*后面添加子标签*			`ul.append("<li>00007</li>");`

*前面插入子标签：传参的方式同append。*



添加兄弟标签（外部操作）

*在标签的后面添加兄弟标签（传参方式同 append*） `$("ul").after("<div>111111</div>");`

*在标签的前面添加兄弟标签(传参方式同 append)*	`$("ul").before("<h2>哈哈哈哈</h2>")`

*将创建的标签添加到指定标签的后面\前面* 	insertAfter  \   insertBefore



 ***父标签***

​     wrap : 包裹、换行。

​     给jquery对象中每一个标签包裹一个父标签

​     `$("ul").wrap("<div></div>");`



​     将jquery对象中所有的标签放在一起，包裹一个父标签。

​     `$("ul").wrapAll("<div></div>");`



​     给jquery对象中每一个标签内所以子标签包裹一个父标签。

​     `$("ul").wrapInner("<div></div>");`



​     将标签解除包裹；把标签从父标签移出，删除父标签。

​     `$("li").unwrap();`



​     ***替换***

​     用指定标签替换原标签

​     `$("ul").replaceWith("<ol></ol>")`

​     意思同上;

​     `$("<ol></ol>").replaceAll("ul")`



​     清空:清空标签内容 ；empty:空

​     `$("li").empty();`



​     remove: 把标签删除

​     返回值：删除元素构成的jquery对象；remove的删除，不会保留被删除标签上的事件、附加数据

​     `$("li").remove();`



​     detach:分开,把标签删除

​     返回值：删除元素构成的jquery对象;detach的删除,会保留被删除标签上的事件、附加数据。

​     `var result = $("li").detach();`

​     `$("body").append(result)`



###### **标签筛选**

`$("ul>li").first()`	第一个

`$("ul>li").last()`	最后一个

*判断是否含有class;返回值是true\false。有一个就返回ture，和some类似*

​	`$("ul>li").hasClass("big");`

*返回值：满足过滤条件的标签构成的jquery对象*

​	`$("ul>li").filter(".big")`

*返回值：满足过滤条件的标签构成的jquery对象*



 判断是否有标签满足条件（类似 数组的some）方法—返回值：true\false  有一个满足就返回true

​	`$("ul>li").is(".big");`

> 例：是否有内容为 0004 的标签
>
>  `var result5 = $("ul>li").is(function (index, ele) {`
>
> ​      `return $(ele).html() == "0004"`
>
> ​    `});`
>
> ​    `console.log(result5);`

***映射***（类似 数组的map方法）——返回值：类数组的对象

>  `var result6 = $("ul>li").map(function (index, ele) {`
>
> ​      `return $(ele).html()`
>
> ​    `});`

***找到后代满足条件的标签***

> 例：找到后代有span的li
>
> `var result7 = $("ul>li").has("span")`

 找到不满足过滤条件的标签构成的jquery对象(类似数组的filter方法)

> ​	`$("ul>li").not(".big")`;

slice(类似数组的slice方法)

> 例：1号元素到4号元素，包含1，不包含4
>
> ​    `var result9 = $("ul>li").slice(1, 4);`

找 ul 标签的子标签 ——~~children~~可以有参数：为过滤含有para1的子标签

> `$("ul").children();`

从自身开始逐级往上找，找到最先匹配的元素(常写 选择器)

> `$("ul").closest("body");`

从后代元素中找满足条件的

> `$("ul").find("li>span");`

​    // next\nextAll\nextUntile: 找后面的相邻标签

​    // prev\prevAll\preUntile: 找前面的相邻标签

​    // parent\parents\parentsUntil: 找上层标签

​    // offsetParent: 找到有定位属性的父标签

> ​    `var res4 = $("ul").next();`

 找和 ul 相邻的所有同层级标签

> $("ul").siblings()



###### **链式调用**

先执行第一个方法调用，得到结果（返回值），再用等到的 返回值 调用第二个方法...

> ​     可以拆分如下方法：
>
> ​     `var result = obj.sayHai();`
>
> ​     `result.introduce();`
>
> ​     sayHai方法没有返回值，也就是undefined;
>
> ​     undefined调用introduce方法失败，因为introduce是obj的方法，只能obj对象调用.
>
> 
>
> ​     如何让obj的方法支持链式调用
>
> ​     让方法内部返回 this

***form***

> serialize:序列化，归档;按照特定的格式组织数据。
>
> ​       快速获取表单数据并以key=value&key=value...的方法组织数据。
>
> ​       注意：表达元素 一定要有name属性；



###### **js动画**

>   show:显示；hide：隐藏
>
> ​       实质是通过 display:none 实现的
>
> ​       `$div.hide();`
>
> ​       `$div.toggle();` //有属性就删除，无属性就添加
>
> 
>
> ​       slideUp():上滑消失(高度变化);
>
> ​       slideDown():下滑显示(高度变化);
>
> ​       slideToggle():滑动显影(高度变化);
>
> ​       `$div.slideUp();`
>
> ​       `$div.slideDown();`
>
> ​       `$div.slideToggle();`
>
> 
>
> ​       fadeOut():淡出（透明度变化）
>
> ​       fadeIn() :淡入
>
> ​       fadeToggle():淡入淡出
>
> ​       `$div.fadeOut();`
>
> ​       `$div.fadeToggle()`
>
> 
>
> ​       变淡到某个值
>
> ​       para1:时间(毫秒为单位)  para2: 透明度值
>
> ​       `$div.fadeTo(2000, 0.6)`
>
> 
>
> 
>
> ​       para1:动画属性对象（px单位可以缺省）不是所有的属性都支持,例如颜色、图形变换。
>
> ​       para2:动画的时间;(以毫秒为单位)
>
> ​       para3:动画结束回调函数
>
> ​       不支持 动画重复、动画方向、动画模式;
>
> ​       支持延迟。



#### **栅格系统**

***bootstrap：是一个响应式的前端UI框架;JS功能依赖于jquery以及popper。支持桌面版以及移动端，并且是移动端优先。***



> ​    响应式：
>
> ​        76px  768px   992px   1200px
>
> ​    (超小屏)  sm(小屏) md(中屏) lg(大屏)   xl(超大屏)
>
> 
>
> ​    与布局相关的样式类：
>
> ​      container：定宽居中，支持响应式。
>
> ​      container-fluid: 宽始终为100%的容器
>
> ​      container-{breakpoint}:
>
> ​        container-sm: 在sm,540; md,720 ; lg,960; xl,1140; <sm,是100%
>
> ​        container-md: 在md,720; lg,960; xl,1140; <md,100%
>
> ​        container-lg: 在lg,宽是960;在xl屏幕上,宽是1140;<lg,宽是100%
>
> ​        container-xl: 再xl屏幕上，宽是1140;<xl时，宽为100%
>
> 
>
> ​    栅格系统:
>
> ​      将一行分为12列;
>
> ​      可以通过样式类 col-sm-num ;col-md-num;...说明这格在不同屏幕上分别占多少比例。
>
> ​      内容格子都需要包含在row中。
>
> ​      一般行包含在容器中。
>
> 
>
> ​      格子默认有左右的内边距，值为15px。
>
> 
>
> ​      等宽布局：col；col-sm; col-md; col-lg; col-xl;
>
> ​      等宽多行布局:可以使用 w-100 样式类，实现宽度100%;没有内容时,就是换行作用。
>
> ​      自定义一格占几列: col-sm-num ;col-md-num;...
>
> ​      由内容撑开宽度：col-sm-auto; col-md-auto;
>
> 
>
> ​      给行添加外边距 mx-屏幕-num;
>
> ​      给格子添加内边距 px-屏幕-num ;
>
> 
>
> ​      快速设置一行有几列：row-cols-num 
>
> 
>
> ​      row上竖直对齐方式: align-items-(start\end\center\stretch(默认值));
>
> ​      格子上单独设置该格的竖直对齐: align-self-(start\end\center\stretch(默认值))
>
> 
>
> ​      水平方向对齐方式：justify-content-(start\end\center\space-around\between);
>
> 
>
> ​      去掉内边距: no-gutters
>
> 
>
> ​      调整弹性元素的顺序: order-num; order-first; order-last;
>
> 
>
> ​      列偏移: offset-屏幕-num;
>
> 
>
> ​      添加自动外边距: ml-屏幕-auto ;
>
> 
>
> ​      列嵌套


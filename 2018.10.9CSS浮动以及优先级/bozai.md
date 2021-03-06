# bo
## CSS使用方法优先级

### CSS引用的优先级

+ 行内样式>内部样式>外部样式
+ **注意：**引入的外部样式表和内部样式表之间的优先级取决于位置的先后！

### CSS选择器权值。
+ 通配符的权重为0
+ 标签选择器的权重为1
+ 类选择器的权重为10
+ ID选择器的权重为100
+ 行内样式的权重是1000
+ @important的权重是至高无上的，无法被超越！

### CSS权重规则 
+ 统计不同的选择器个数
+ 每类选择器的个数乘以相应的权重
+ 所有的值加在一起得出选择器的权重。

### CSS优先级规则
+ 同一个样式表里，权重相同，取就近原则。
+ 同一个样式表里，权重不同，取级别大的执行。
+ **注意：**最后定义的优先级最高（就近原则。

## CSS继承与层叠

### CSS层叠
+ 可以继承多个样式
+ 不冲突的时候，多个样式都可以起作用
+ 冲突时候，按照样式规则的优先级来应用！

### CSS继承
+ 从父类继承部分CSS属性（大多是字体方面
+ **注意1：**a标签不能继承父元素中的文字颜色
+ **注意2：**h标签不能继承文字的大小


## 浮动
+ 我们之前接触的都是标准流（文档流），标准流就是，块级元素就是霸道独占一行有宽高，行内快就是有宽高但是我允许你和我一起在同一行，行内就是可怜弱小又无助，只能被内容撑着，宽高没作用。
+ 浮动的意思，就是浮起来了，脱离了文档流！你可以理解为，他们在表现形式上，好像成为了，inline-block,但是绝对不要真的认为他就是inline-block，i-b他是标准流，而浮动是脱离文档流，并且浮动会带来一些奇奇怪怪的事情（例如，坍塌以及同一行盒子高度不同时候排列的顺序。

### 浮动的特点
+ 浮动找浮动，不浮动找不浮动
+ 浮动只影响后面的元素
+ 浮动以元素顶部为基准对齐
+ 浮动可是实现模式转换（span 设置浮动可以设置宽高）
+ 让块级元素在一行显示

### 浮动的用处

+ 制作导航栏
+ 网页布局

### 浮动带来的影响
+ 标准流下，当父容器没有设置高度，里面的盒子会将父容器的高度撑开。
+ 浮动脱离文档流情况：父容器没有高度，下面的盒子会跑到浮动的盒子下面。出现这种情况，我们需要清除浮动!.

#### 清除浮动的几种方式
+ 既然是父类没有高度原因导致，那我们可以选择给父类添加高度嘛！（缺点：定死了高度，但是开发过程中，很多时候高度是不要定死的
+ 在浮动元素后面写一个多余的div，然后设置样式`clear:both`，（缺点：添加了不需要的节点。如果页面浮动布局多，就要增加很多空div。
+ 给父类设置`overflow:hidden`,(缺点，不可以和定位搭配使用，因为超出部分就一刀切了！如果你想知道为什么他可以清除浮动，那么需要引入块格式化上下文(BFC)这个概念，这点就不多说了，也有相当多的前端开发者，不懂BFC - -)
+ 父级div定义伪类清除` .clearfloat:after{display:block;clear:both;content:"";visibility:hidden;height:0}`,（缺点，新手不知道啥是伪类。但是是最推荐的。

## 定位（position
决定元素如何定位，并且通过top/right/bottom/left来实现位置的改变

### 定位的分类
+ static 静态定位（标准流，默认的，不必理会
+ absolute 绝对定位 
+ relative 相对定位
+ fixed 固定定位

### absolute(绝对定位)

+ 如果父类没有定位，那么就以浏览器左上角为基准！
+ 如果父类有定位，那么以父类的定位为基准
+ 绝对定位不占空间，（和浮动一样，
+ 绝对定位会使行内元素的宽高生效，同时也会让块级元素的独占一行失效。

### relative（相对定位
+ 相对定位以元素自身的位置为基准设置位置
+ 相对定位占位置
+ 一般子元素设置相对定位，父元素设置绝对定位（子绝父相）

### fixed（固定定位
+ 不占位置
+ 不管怎么样，我就在这个窗口的某一个地方，定死在这里。





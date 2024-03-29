# 简介
这是一个 css 布局练习仓库，每个练习具体要求见后文。练习成对，即奇数为需要掌握的知识点，偶数只需简单改动布局顺序即可。 所有练习以如下HTML结构为基础，千万不要改动，否则失去练习的意义！
```
<div id="container">
    <div id="header">header</div>

    <div id="wrapper">
        <div id="content">content</div>
    </div>
    
    <div id="navigation">navigation</div>
    <div id="extra">extra stuff</div>
    <div id="footer">footer</div>
</div>
```

## 练习题目及图示
### 1. Three percentage columns(n.1)
#### 要求：  
1.wrapper 居中，且占据 50% 的宽度。  
2.左侧navigation，右侧extra，分别位于 wrapper 两侧，各占
25%  

#### 效果图：  

![image](https://github.com/xiaoxiaomuyu123/layoutExercise/blob/master/layoutExercisePic/1.png)

#### 解题感想：
注意盒模型的宽度，我们设置的 div 的 width 是设置的 div 
内容（content）的宽度，而不是盒模型的宽度。
这个题目中，若设置 navigation 的宽度是 25%，只能说明他的
文字部分所占的宽度比例是 25%，至于整个 navigation 占据页面
布局的宽度，就不是 25% 了，还和 navigation 的 padding
有关。也就是说，标准盒模型尺寸的计算是：  
盒子模型的实际宽度:width+左右padding+左右border  
盒子模型的实际长度:width+上下padding+上下border  
boder 以内的盒子区域 统称为盒子的可视区域。  

要想让内容区的文字，不紧紧贴着 div 边框，也就是让文字和 div
的边框有一定的距离，可以设置对应的 p 元素的 maigin 值，
不要设置 div 本身的 margin 或者 padding 值，因为设置了
div 本身的padding 值会导致该 div 的盒模型可视面积变化，
容易影响他的兄弟元素，在这里用的是 float 属性，就会遮挡其他的
兄弟元素；若是普通的文档流布局，就会挤开其他的兄弟元素，影响其他
兄弟元素的位置，从而影响布局。 

有关 margin-left 的理解：子元素的 margin-left，width，margin-right
都可以设置成 auto。有以下几种情况：   
情况一：三者之一设置成 auto，那么会使这个子元素的宽度加上 margin 等于父元素
的 width；   
情况二：margin-left，width，margin-right都设置了特定值，但是七大属性总和不等于父级元素的width。
这种情况下： 在FF中，margin-right的值为开发者设定的值，在Chrome中，margin-right被强制为auto 
情况三：width 设置成 auto，如果margin-left和margin-right都设置特定值，width设置为auto，
则width将会等于某个特定值以达到父级元素的width。 
 
负外边距：当margin，padding，border，width 这几个属性都大于零的时候，加起来
一定会等于父元素的 width，但是可以通过设置 负外边距 得到比父元素 width 更大
的区域。此时依旧是 margin，padding，border，width 的属性值之和 = 父级元素的宽度
当元素在文档流中，设置了 margin 为负值，会导致该元素的边界往里收，文档流中
只兄弟元素只认识边界 margin 这个边界，不会认识该元素的 width
当元素设置浮动之后，若 margin-left 设置成负值，会以本身的 border 往左移。

### 2. Three percentage columns(n.2)
#### 要求：
在 1 的基础上调换 navigation 和 extra
#### 效果图： 

![image](https://github.com/xiaoxiaomuyu123/layoutExercise/blob/master/layoutExercisePic/2.png)

#### 解题感想：
元素设置 float 以后，一定要设置宽度。

### 3. Three percentage columns(n.3)
#### 要求：
1. wrapper 左对齐且占据50%宽度
2. extra、navigation宽度25%，依次位于content右侧
#### 效果图： 

![image](https://github.com/xiaoxiaomuyu123/layoutExercise/blob/master/layoutExercisePic/3.png)

### 4. Three percentage columns(n.4)
#### 要求：
在 3 的基础上调换 navigation 和 extra
#### 效果图： 

![image](https://github.com/xiaoxiaomuyu123/layoutExercise/blob/master/layoutExercisePic/4.png)

### 5. Three percentage columns(n.5)
#### 要求：
1. wrapper 右对齐且占据50%宽度
2. extra、navigation宽度25%，依次位于content左侧
#### 效果图：  

![image](https://github.com/xiaoxiaomuyu123/layoutExercise/blob/master/layoutExercisePic/5.png)

### 6. Three percentage columns(n.6)
#### 要求：
在5的基础上，调换navigation和extra
#### 效果图：
  
![image](https://github.com/xiaoxiaomuyu123/layoutExercise/blob/master/layoutExercisePic/6.png)

### 7. Three fixed columns(n.7)
#### 要求：
1. container 宽度700px且居中
2. wrapper 居中且宽度400px
3. extra、navigation 150px，依次位于content两侧
#### 效果图：

![image](https://github.com/xiaoxiaomuyu123/layoutExercise/blob/master/layoutExercisePic/7.png)

#### 解题感想：
三栏布局套路：这三栏都是 flaot 布局。中间一栏的要想居中，不能用 margin ： 0 auto；
此时中间一栏的剧中由两种办法， 
一种是自己手动计算，左右两侧的边栏各自是多少 px，设置中间边栏的 maigin 
左右是刚刚计算出的 px，这种方法可以计算出两边侧栏的 margin-left 的负值具
体时间多少 px，从而让后面的 div 成为两边的侧栏； 
另一种是在设置中间栏的左右 margin 时，用 calc（）函数来自动计算。对于这个题目的数据
来说，用 cacl（）函数计算的方法是，用 整个屏幕的 50% 宽度 减去 中间栏宽度的
一半，就能得到中间边栏距离屏幕两边的距离了，这样做适应性更强。
 
margin: 0 auto 设置元素水平居中要满足以下条件才能成立：
1. 该元素必须设定一个固定的宽度，否则居中无效
2. 该元素不能是浮动或者绝对定位，否则无效。float 会使元素脱离当前的文档流。

### 8. Three fixed columns(n.8)
#### 要求：
在7的基础上，调换navigation和extra
#### 效果图：

![image](https://github.com/xiaoxiaomuyu123/layoutExercise/blob/master/layoutExercisePic/8.png)

### 9. Three fixed columns(n.9)
#### 要求：  
1. container 宽度 700px，居中  
2. wrapper 左对齐，宽度 400px
3. navigation extra 宽度 150px，依次居于右侧

#### 效果图：  

![image](https://github.com/xiaoxiaomuyu123/layoutExercise/blob/master/layoutExercisePic/9.png)

#### 解题感想：
float 的几个块元素会尽量分布在同一行

### 10. Three fixed columns(n.10)
#### 要求：
在 9 的基础上，调换navigation和extra
#### 效果图：

![image](https://github.com/xiaoxiaomuyu123/layoutExercise/blob/master/layoutExercisePic/10.png)

#### 解题感想：
两种方法： 
1. 让 navigation float ：right；extra float ：left；就解决啦
2. 还是让 navigation 和 extra 两个都是 float:left，但是呢，要调节
margin-left 值。navigation 设置 150px，这样可以给 extra 150px 的
位置，extra 设置成 -300px，原因是，当设置了 navigation margin-left
为 150px 的时候，navigation 盒模型就会占据上面一行，把 extra 挤下来了
extra 就要设置成 -300px，才能回到第一行。

### 11. Three fixed columns(n.11)
#### 要求：  
1. container 宽度 700px，居中  
2. wrapper 右对齐，宽度 400px
3. navigation extra 宽度 150px，依次位于左侧

#### 效果图：  

![image](https://github.com/xiaoxiaomuyu123/layoutExercise/blob/master/layoutExercisePic/11.png)

### 12. Three fixed columns(n.12)
#### 要求：
在 11 的基础上，调换navigation和extra
#### 效果图：

![image](https://github.com/xiaoxiaomuyu123/layoutExercise/blob/master/layoutExercisePic/12.png)

### 13. Liquid, secondary columns fixed-width (n.13)
#### 要求：   
1. wrapper 居中，宽度自适应
3. navigation extra 宽度 200px，依次位于两侧

#### 效果图：  

![image](https://github.com/xiaoxiaomuyu123/layoutExercise/blob/master/layoutExercisePic/13.png)

#### 解题感想：
这应该是传说中的圣杯布局或者双飞翼布局。其中设置了 navigation 的 margin-left
为 -100%，使得 navigation 能够移动到 wrapper 这一行的最左边。原理是：
margin-left 的值 如果是 px ，那么直接就是在包裹着他的父元素内向左移动
那么多 px 的距离，本行不够，就向上一行移动来凑。如果 margin-left 设置的是
百分数，要注意，这个时候的百分数是相对 navigation 的父元素来说的。所以设置
-100% 就是向左移动一个父元素的宽度。但是要注意，extra 的 margin-left 的
负值就不能用百分数来表示了，原因是，此时中间的元素宽度不确定，那么百分数的
分母就不确定，不能具体的计算出 extra 的上移百分数，但是却可以轻松地算出他上移
具体 px 是多少。

### 14. Three fixed columns(n.14)
#### 要求：
在 13 的基础上，调换navigation和extra
#### 效果图：

![image](https://github.com/xiaoxiaomuyu123/layoutExercise/blob/master/layoutExercisePic/14.png)

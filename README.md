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


### 2. Three percentage columns(n.1)
#### 要求：
在 1 的基础上调换 navigation 和 extra
#### 效果图： 

![image](https://github.com/xiaoxiaomuyu123/layoutExercise/blob/master/layoutExercisePic/2.png)

#### 解题感想：
元素设置 float 以后，一定要设置宽度。

### 3. Three percentage columns(n.1)
#### 要求：
1. wrapper 左对齐且占据50%宽度
2. extra、navigation宽度25%，依次位于content右侧
#### 效果图： 

![image](https://github.com/xiaoxiaomuyu123/layoutExercise/blob/master/layoutExercisePic/3.png)

### 4. Three percentage columns(n.1)
#### 要求：
在 3 的基础上调换 navigation 和 extra
#### 效果图： 

![image](https://github.com/xiaoxiaomuyu123/layoutExercise/blob/master/layoutExercisePic/4.png)

### 5. Three percentage columns(n.1)
#### 要求：
1. wrapper 右对齐且占据50%宽度
2. extra、navigation宽度25%，依次位于content左侧
#### 效果图：  

![image](https://github.com/xiaoxiaomuyu123/layoutExercise/blob/master/layoutExercisePic/5.png)

### 6. Three percentage columns(n.1)
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





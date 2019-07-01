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






#### position属性
在网络中Y轴向下为正，X轴向右
##### 五个属性值：relative absolute fixed static  sticky  

##### static定位
- HTML 元素的默认值，即没有定位，遵循正常的文档流对象。   
静态定位的元素不会受到 top, bottom, left, right影响。   
```
div.static {   
position: static;    
border: 3px solid #73AD21;     
}
```
##### 相对定位relative：相对于正常位置进行定位;升起来，但不脱离文档流
###### 场景
1. 用于做位移  （很少用）
2. 用于给absolute元素做父元素
```
h2.pos_left  
{  
	position:relative;  
    left:-20px;  
}   
//左移20个像素
>h2.pos_right   
{   
	position:relative;   
	left:20px;   
}   
//向元素的原始左侧位置增加20px;右移20px
```
```
>h2.pos_top   
{    
  position:relative;   
	top:50px;   
}   
//向元素的原始位置向下增加50px;下移50px
```
```
>h2.pos_top  
{	   
  position:relative;  
	top:-50px;  
}

//向元素的原始位置向上增加50px;上移50px;	top:-50px; 从元素的原始位置减去50px   
```
##### 绝对定位 absolute
###### 场景
1. 脱离原来的位置，另起一层
2. 对话框的关闭按钮  
3. 鼠标提示语  

- 绝对定位的元素的位置相对于最近的已定位父元素，如果元素没有已定位的父元素，那么它的位置相对于&lt;html &gt;:  
- 定位基准是祖先里的非static,可以是relative，fixed，sticky
- 要补上top和left，否则有些浏览器会出问题
```
{   
	position:absolute;   
	left:100px;//向右移100px   
	top:150px;//向下移150px   
}
```
######  absolute 定位的元素和其他元素重叠 定位使元素的位置与文档流无关
###### Fixed定位的元素和其他元素重叠  Fixed定位使元素的位置与文档流无关，因此不占据空间

###### fixed定位 元素的位置相对于浏览器窗口是固定位置，定位基准是viewport（视口）
###### 场景
1. 固定的广告位置  
2. 回到顶部的按钮  

- 即使窗口是滚动的它也不会移动：   
- 但是有些特殊的css属性存在，就不相对于视口定位，如transform: scale(0.9);
- 要补上top和left，否则有些浏览器会出问题 
- 手机上尽量不要用这个属性，坑很多，搜索【移动端fixed】
```
p.pos_fixed   
{    
	position:fixed;    
	top:30px;    
	right:5px;    
}
```
##### 粘性定位sticky
###### 场景
1. 用于导航栏 
- 兼容性差
```
div.sticky {    
  position: -webkit-sticky;     
  position: sticky;    
  top: 0;    
  padding: 5px;   
  background-color: #cae8ca;   
  border: 2px solid #4CAF50;   
}
```

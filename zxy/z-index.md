# z-index
## 含义

z顺序，一般那个大那个就可以覆盖哪个小的

## 属性值

auto, inhefit, integer

特性: 可负值，可animation(css3), 与定位元素配合（css2.1）, 还有其他元素起作用（[css3](http://www.cnblogs.com/s1nker/p/4835079.html)）

## 与定位元素

<img src="http://img.mukewang.com/585d44b700018a9912800720.jpg" alt="与定位元素" title="与定位元素" width="300"/>

auto等同于0

### 无嵌套
1. 相等，后来居上
2. 不等，谁大谁上

### 有嵌套
1. 看祖先元素大小

## 层叠上下文

HTML元素三维概念

元素在z轴有值了

页面**根元素**自动具有层叠上下文

定位元素带值z-index

1. 可以嵌套，祖先元素和后代元素都可以有自己的

2. 和兄弟元素没关系，只影响后代元素

3. 自成体系

## 层叠水平

在z轴上显示顺序

1. 普通元素都有

2. 后来居上

3. 谁大谁上

## 层叠顺序

元素发生层叠时，特定的垂直显示顺序

1. 正z-index
2. z-index：0或auto
3. inline或inline-block
4. float
5. block
6. 负z-index
7. background、border

<img src="http://img.mukewang.com/585d46e500014fd112800720.jpg" alt="层叠顺序" title="层叠顺序" width="300"/>

意义

规范元素重叠时候呈现规则

内联元素覆盖浮动元素

内容层叠水平高

<img src="http://img.mukewang.com/585d47080001bd3b12800720.jpg" alt="内容层叠水平高" title="内容层叠水平高" width="300"/>

## z-index与层叠上下文
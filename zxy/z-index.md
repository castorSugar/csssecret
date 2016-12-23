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

1. 定位元素默认z-index:auto
2. z-index不为auto的定位元素会创建层叠上下文
3. z-index层叠顺序的比较止步于父级层叠上下文


<img src="http://img.mukewang.com/585d48de0001ef5a12800720.jpg" alt="z-index不为auto的定位元素会创建层叠上下文" title="z-index不为auto的定位元素会创建层叠上下文" width="300"/>


<img src="http://img.mukewang.com/585d496d0001b0b412800720.jpg" alt="z-index层叠顺序的比较止步于父级层叠上下文" title="z-index层叠顺序的比较止步于父级层叠上下文" width="300"/>

## 带某些css3属性的元素参与层叠上下文

1. z-index值不为auto的flex属性（父元素display:flex|inline-flex）

	<img src="http://img.mukewang.com/585d4a600001887512800720.jpg" alt="父元素display:flex" title="父元素display:flex" width="300"/>

2. opacity /= 1

	<img src="http://img.mukewang.com/585d4a7d0001977412800720.jpg" alt="opacity /= 1" title="opacity /= 1" width="300"/>

3. transform /= none

	<img src="http://img.mukewang.com/585d4ab4000100ec12800720.jpg" alt="transform /= none" title="transform /= none" width="300"/>

4. min-blend-mode /= normal

	<img src="http://img.mukewang.com/585d4af30001220912800720.jpg" alt="min-blend-mode /= normal" title="min-blend-mode /= normal" width="300"/>

5. filter /= none

	<img src="http://img.mukewang.com/585d4b2a0001104412800720.jpg" alt="filter /= none" title="filter /= none" width="300"/>

6. isolation: isolate

	<img src="http://img.mukewang.com/585d4b6f0001989a12800720.jpg" alt="isolation: isolate" title="isolation: isolate" width="300"/>

7. position: fixed(webkit)

	<img src="http://img.mukewang.com/585d4ba70001001a12800720.jpg" alt="position: fixed(webkit)" title="position: fixed(webkit)" width="300"/>

8. will-change

	<img src="http://img.mukewang.com/585d4bd700016cc012800720.jpg" alt="will-change" title="will-change" width="300"/>

9. -webkit-overflow-scrolling: touch

## 与其他css属性层叠上下文

1. 不支持z-index的层叠上下元素的层叠顺序均是z-index:auto级别

	<img src="http://img.mukewang.com/585d4d1c0001e40312800720.jpg" alt="不依赖z-index的层叠上下文" title="不依赖z-index的层叠上下文" width="300"/>
2. 依赖z-index的层叠上下文元素的层叠顺序取决于z-index值
	
	position： relative|absolute|fixed

	display:　flex|inline-flex容器的子flex项

	<img src="http://img.mukewang.com/5847ee640001e47612800720.jpg" alt="取决于z-index值" title="取决于z-index值" width="300"/>

**图片元素opacity变化**

文字元素和图片元素作为兄弟，图片添加动画效果淡入淡出，最后文字跑到后面

opacity:1，没层叠上下文，后来居上，在文字上

其他opacity值，有层叠上下文，如同z-index:auto级别，在文字下

## 实践

1. 最小化影响
	
	避免嵌套层叠关系混乱
	1. 不使用定位属性
	2. 定位属性从大容器平级分离为私有小容器

2. 不犯二
	
	对于非浮层元素，避免设置z-index值，其值不超过2

3. 组件层级计数器

	避免浮层组件因为z-index被覆盖

	获得body下子元素的最大z-index

4. 可访问性隐藏
	
	z-index：-1（ie7-)
	
	<img src="http://img.mukewang.com/585d50bb0001e26912800720.jpg" alt="可访问性隐藏" title="可访问性隐藏" width="300"/>
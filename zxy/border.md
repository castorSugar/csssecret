# border
## border-width 不能用百分比表示

由使用场景决定的,**因为边框大小不会因为元素大小变化而成比例变化**
类似的还有outline,border-shadow,text-shadow

## 支持关键字
thin(1px),medium(3px,默认),thick(5px)

## 类型
### solid 实线

### dashed 虚线
>差异
>
>chrome、Firefox 宽高 3:1
>ie 宽高 2:1

### dotted 点线
>差异
>
>chrome、Firefox 方形
>ie 圆形

*ie8- 实现圆角*

		.box{
			width:150px;
			height:150px;
			overflow:hidden;
		}

		.dotted{
			width:100%;
			height:100%;
			border:149px dotted #cd0000;
		}


<img src="http://img.mukewang.com/58568c320001f61212800720.jpg" alt="ie8- 实现圆角" title="ie8- 实现圆角" width="300"/>

### double 双线

计算规则 

上下线宽度永远相等，中间间隔+-1

1px = 0 + 1 + 0

2px = 1 + 0 + 1

3px = 1 + 1 + 1

4px = 1 + 2 + 1

5px = 2 + 1 + 2

*实现三道杠*

		.three-bars{
			width: 120px;
			height: 20px;
			border-top: 60px double;
			border-bottom: 20px solid;
		}

<img src="http://img.mukewang.com/58568d11000145f912800720.jpg" alt="实现三道杠" title="实现三道杠" width="300"/>


### 其他
inset 内凹

outset 外凹

groove 沟槽

ridge 山脊

## border-color和color

border-color 默认颜色是 color
相同的有box-shadow,text-shadow

border和box-shadow默认的颜色就是当前的文字颜色

currentColor（css3）可以设置默认颜色

*变色代码简易*


<img src="http://img.mukewang.com/58568e5f0001998512800720.jpg" alt="变色代码简易" title="变色代码简易" width="300"/>

## border和background

background(css2.1)只能相对于左上角数值定位

*相对于右侧定位*

*100% 右侧定位不计算border区域*

<img src="http://img.mukewang.com/5856912c0001da4612800720.jpg" alt="相对于右侧定位" title="相对于右侧定位" width="300"/>

## border与三角形

*solid运用*

<img src="http://img.mukewang.com/5856921a00010d7212800720.jpg" alt="三角形" title="三角形" width="300"/>

*近似圆角*

<img src="http://img.mukewang.com/585692d2000127f612800720.jpg" alt="近似圆角" title="近似圆角" width="300"/>

## border和透明边框

ie7+ 兼容

相对于右侧定位、三角形，梯形

*增加响应区域*

<img src="http://img.mukewang.com/585693d70001176912800720.jpg" alt="增加响应区域" title="增加响应区域" width="300"/>

*增加可视渲染区域*

<img src="http://img.mukewang.com/5856946c0001345412800720.jpg" alt="增加可视渲染区域" title="增加可视渲染区域" width="300"/>

## border和布局

*有限标签下的标题栏*

*border 实现等高两栏布局*

<img src="http://img.mukewang.com/5856954e0001f69212800720.jpg" alt="等高两栏" title="等高两栏" width="300"/>

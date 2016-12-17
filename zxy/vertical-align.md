#vertical-align属性

## 属性值
1. 继承 -- inherit

2. 线 -- baseline,top,middle,bottom

3. 文本 -- text-top,text-bottom

4. 上标下标 -- sub,super

5. 数值百分比 -- 20px,2em,20%

**百分比值相对于line-height计算**

>百分比值共性

>a. 都带数字

>b. 都支持数值
margin,letter-spacing,word-spacing,vertical-align

>c. 行为表现一致

## 起作用前提
###默认元素

>inline -- img,span,strong,em,未知元素

>inline-block -- input,button

>table-cell -- td

### 改变属性
>display:block

>position:absolute

>float:left

### 不起作用 
>不是不起作用，是太短 -- 行高？ie7+

>table-cell作用到自身元素

### 个数不定文字内容和图片垂直居中对齐
style

	.test-list > span{display:inline-block; width: 250px; vertical-align:middle;}
	.test-list > img{vertical-align:middle}

html

	<div class="test-list">
		<span>内容</span>
		<img src="http://img4.imgtn.bdimg.com/it/u=2968019053,3099143592&fm=11&gp=0.jpg">
	</div>

## vertical-align和line-height在内联元素实际存在

### 消灭空白

	img{
		vertical-align:baseline;
		line-heigth:1.5;
		font-size:24px;
		/* display:block; margin:auto; */
		/* vertical-align:middle; */
		/* line-height:0; */
		/* font-size:0; */
	}

### 近似垂直居中

	img{
		vertical-align:middle;
		line-height:250px;
	}

### 兼容ie6
	<p>
		<img>
	<p>

### 两端对齐
style

	img{width:250px;}
	.justify-fix{display:inline-block; width: 250px;}
html

	<p style="text-align:justify;">
		<img src="http://img4.imgtn.bdimg.com/it/u=2968019053,3099143592&fm=11&gp=0.jpg">
		<img src="http://img4.imgtn.bdimg.com/it/u=2968019053,3099143592&fm=11&gp=0.jpg">
		<img src="http://img4.imgtn.bdimg.com/it/u=2968019053,3099143592&fm=11&gp=0.jpg">
		<img src="http://img4.imgtn.bdimg.com/it/u=2968019053,3099143592&fm=11&gp=0.jpg">
		<i class="justify-fix"></i>
		<i class="justify-fix"></i>
		<i class="justify-fix"></i>
	</p>

### 一个inline-block元素，如果里面没有inline内联元素，或者overflow不是visible，则该元素的基线就是其margin底边缘，否则，其基线就是元素里面最后一行内联元素的基线。

## vertical-align线性属性值
### vertical-align:bottom
1. inline

元素底部和整行底部对齐

<img src="http://img.mukewang.com/584f8e1d000116fb12800720.jpg" alt="元素底部和整行底部对齐" title="元素底部和整行底部对齐" width="300"/>

2. table-cell

单元格底padding边缘和表格行底部对齐

<img src="http://img.mukewang.com/584f8ebc00010dd512800720.jpg" alt="单元格底padding边缘和表格行底部对齐" title="单元格底padding边缘和表格行底部对齐" width="300"/>

### vertical-align:top
1. inline

元素顶部和整行顶部对齐

<img src="http://img.mukewang.com/584f8f0100017bc512800720.jpg" alt="元素顶部和整行顶部对齐" title="元素顶部和整行顶部对齐" width="300"/>

2. table-cell

单元格顶padding边缘和表格行顶部对齐

<img src="http://img.mukewang.com/584f8f210001e3ea12800720.jpg" alt="单元格顶padding边缘和表格行顶部对齐" title="单元格顶padding边缘和表格行顶部对齐" width="300"/>

### vertical-align:middle
1. inline

元素垂直中心点和父元素基线上1/2x-height处对齐

<img src="http://img.mukewang.com/584f8fcb000104e312800720.jpg" alt="元素垂直中心点和父元素基线上1/2x-height处对齐" title="元素垂直中心点和父元素基线上1/2x-height处对齐" width="300"/>

## vertical-align文本类属性值
### vertical-align:text-top

盒子顶部和父级content area顶部对齐

### vertical-align:text-bottom

盒子底部和父级content area底部对齐

<img src="http://img.mukewang.com/584f91840001cf0f12800720.jpg" alt="vertical-align文本类属性值" title="vertical-align文本类属性值" width="300"/>

<img src="http://img.mukewang.com/584f92890001624a12800720.jpg" alt="表情图片与文字对齐效果" title="表情图片与文字对齐效果" width="300"/>


## vertical-align上下标类属性值
### vertical-align:super
<sup\>标签

提高盒子基线到父级合适上标基线位置

### vertical-align:sub
<sub\>标签

降低盒子基线到父级合适下标基线位置

<img src="http://img.mukewang.com/585558180001554b12800720.jpg" alt="vertical-align上下标类属性值" title="vertical-align上下标类属性值" width="300"/>

## vertical-align前后行为表现不一致

### 完全垂直居中

	p{line-height:250px; /* font-size:0; */}
	img{vertical-align:middle;}
	img + span{vertical-align:middle;}

### text-bottom baseline

	p{line-height:250px;}
	img{vertical-align:text-bottom;}


***关注当前元素和父级***

***前后没有直接影响***

<img src="http://img.mukewang.com/584f9aa30001eb9b12800720.jpg" alt="text-bottom baseline" title="text-bottom baseline" width="300"/>

## vertical-align实际应用
### 小图片和文字的对齐

负值 14px文字

img{vertical-align:-5px;}

### 不定尺寸图片或多行文字垂直居中

主体元素inline-block

添加height:100%;width:0辅助元素

同时vertical-align:middle


<img src="http://img.mukewang.com/584fd2010001d4a912800720.jpg" alt="不定尺寸图片或多行文字垂直居中" title="不定尺寸图片或多行文字垂直居中" width="300"/>
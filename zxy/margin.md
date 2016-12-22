# margin
## 改变容器尺寸
### 可视尺寸 -- clientWidth
1. 没有设定width/height

2. display:block

3. 只适用水平方向

**一侧定宽自适应布局**

<img src="http://img.mukewang.com/585bad760001274b12800720.jpg" alt="一侧定宽自适应布局" title="一侧定宽自适应布局" width="300"/>

### 占据尺寸 -- outerWidth （假设）

1. block/inline-block都行

2. width/height无关

3. 水平、垂直方向都行

**滚动容器上下留白**


<img src="http://img.mukewang.com/585badd10001160112800720.jpg" alt="滚动容器上下留白" title="滚动容器上下留白" width="300"/>

## margin和百分比

### 普通元素、绝对定位元素
### 水平方向、垂直方向

1. 普通元素相对于容器**宽度**计算

<img src="http://img.mukewang.com/585baeec0001c09e12800720.jpg" alt="普通元素" title="普通元素" width="300"/>

2. 绝对定位元素相对于第一个定位祖先元素**宽度**计算

<img src="http://img.mukewang.com/585baf0a0001eae212800720.jpg" alt="绝对定位元素" title="绝对定位元素" width="300"/>

**宽高2:1自适应矩形**

<img src="http://img.mukewang.com/585baf5900012f6b12800720.jpg" alt="宽高2:1自适应矩形" title="宽高2:1自适应矩形" width="300"/>


## margin 重叠
1. block水平元素（不包括float和absolute）
2. 只发生在**垂直**方向（如果不考虑writing-mode）

### 发生地方
1. 相邻兄弟元素
2. 父级和第一个或者最后一个子元素
3. 空block元素

<img src="http://img.mukewang.com/585bb11d00015d3112800720.jpg" alt="父级和第一个或者最后一个子元素" title="父级和第一个或者最后一个子元素" width="300"/>

<img src="http://img.mukewang.com/585bb2730001a7f312800720.jpg" alt="空block元素margin重叠" title="空block元素margin重叠" width="300"/>

### 清除影响
#### 干掉margin-top重叠
1. 父级是块级格式化上下文元素，如：overflow:hidden
2. 父级有border-top
3. 父级有padding-top
4. 父级和第一个子元素有inline元素分割，如：&nbsp;

<img src="http://img.mukewang.com/585bb1f20001236812800720.jpg" alt="干掉margin-top重叠" title="干掉margin-top重叠" width="300"/>

#### 干掉margin-bottom重叠
1. 父级是块级格式化上下文元素，如：overflow:hidden
2. 父级有border-bottom
3. 父级有padding-bottom
4. 父级和最后一个子元素有inline元素分割，如：&nbsp;
5. 父级有声明height

<img src="http://img.mukewang.com/585bb2130001207912800720.jpg" alt="干掉margin-bottom重叠" title="干掉margin-bottom重叠" width="300"/>

#### 空block不重叠
1. 有boder
2. 有padding
3. 包含inline
4. 有height

<img src="http://img.mukewang.com/585bb2b2000165c912800720.jpg" alt="空block不重叠" title="空block不重叠" width="300"/>

### margin重叠计算
1. 正正取大
2. 正负相加
3. 负负取小

<img src="http://img.mukewang.com/585bb35a00014f9212800720.jpg" alt="margin重叠计算" title="margin重叠计算" width="300"/>

### margin重叠意义
1. 连续段落或者列表，其中首尾项和其他兄弟标签排版自然
2. 空div插入到任意地方，不影响原来布局
3. 遗落空任意多个p，不影响原来排版

### margin重叠实践
带上下margin，最后一个元素移除或位置调换，不影响原布局

<img src="http://img.mukewang.com/585bb3bd000178e112800720.jpg" alt="margin重叠实践" title="margin重叠实践" width="300"/>

## margin:auto

### 作用机制
没有设置width/height元素，会自动填充对应方位

有设置width/height元素，不会自动填充，出现空缺空间

margin:auto自动根据空缺空间产生距离

<img src="http://img.mukewang.com/585bb5cb0001bac512800720.jpg" alt="作用机制" title="作用机制" width="300"/>

如果一侧定值，一侧auto，auto为剩余空间大小（上限）

如果两侧auto，平方剩余空间

<img src="http://img.mukewang.com/585bb702000150db12800720.jpg" alt="居中" title="居中" width="300"/>

### 垂直居中
父级有heigth，有writing-mode:vertical-lr，子元素有高


<img src="http://img.mukewang.com/585bb7f8000197f512800720.jpg" alt="垂直居中" title="垂直居中" width="300"/>

父级relative, 子元素absolute,拉伸top/right/bottom/left:0(ie8+)


<img src="http://img.mukewang.com/585bb83c00011b3212800720.jpg" alt="子元素absolute" title="子元素absolute" width="300"/>

## margin负值

### 两端对齐

父级带个margin-right：负值

抵消最后一个子元素margin-right：正值

<img src="http://img.mukewang.com/585bb9db0001bf8612800720.jpg" alt="两端对齐" title="两端对齐" width="300"/>

### 等高布局

父级块状格式化，margin预留空间，padding填充

<img src="http://img.mukewang.com/585bba5a0001aa2012800720.jpg" alt="等高布局" title="等高布局" width="300"/>

### 两栏自适应布局

**不改变DOM位置**

左边元素添加width：100%,float:left容器，（ie7-),元素margin-right：右边尺寸空位

右边元素float:left,margin-left:-右边尺寸空位

<img src="http://img.mukewang.com/585bbaed0001cc7912800720.jpg" alt="不改变DOM位置" title="不改变DOM位置" width="300"/>

ie8+

	<div class="" style="float: left; width: calc(100% - 170px);">
	<p style=" background-color: #f00;">some word</p>
	</div>
	<img src="" alt="" style="float: left; width: 150px;">

## margin 失效

### inline元素的垂直margin

1. 不是替换元素，不是img

2. 正常书写模式

<img src="http://img.mukewang.com/585bbc610001939312800720.jpg" alt="inline元素" title="inline元素" width="300"/>

### 重叠

### display:table\table-cell

<img src="http://img.mukewang.com/585bbcae000166f412800720.jpg" alt="display:table\table-cell" title="display:table\table-cell" width="300"/>

**例外生效（替换元素）**

<img src="http://img.mukewang.com/585bbd0e0001e33312800720.jpg" alt="替换元素" title="替换元素" width="300"/>

### position

绝对定位元素非定位方位的margin值“无效”一直有效，不过影响不到兄弟元素

<img src="http://img.mukewang.com/585bbf7a00019d8312800720.jpg" alt="position" title="position" width="300"/>

<img src="http://img.mukewang.com/585bbdc90001fc2612800720.jpg" alt="position" title="position" width="300"/>

### 不够大

块状格式化元素，相对容器起作用，兄弟元素需要足够大距离才影响到

<img src="http://img.mukewang.com/585bbe540001892712800720.jpg" alt="不够大" title="不够大" width="300"/>

### 内联特性

相对于基线对齐，margin超过数值部分不起作用

<img src="http://img.mukewang.com/585bbe980001a53112800720.jpg" alt="内联特性" title="内联特性" width="300"/>

## margin-start/margin-end

1. 正常流，margin-start等同于margin-left，两者重叠不累加

2. 从右往左，margin-start等同于margin-right

3. 垂直流(writing-mode:vertical-*)， margin-start等同于margin-top

<img src="http://img.mukewang.com/585bc05e0001920312800720.jpg" alt="margin-start" title="margin-start" width="300"/>

## margin-befor/margin-after

1. 正常流，margin-before等同于margin-top
2. 正常流，margin-after等同于margin-bottom

## margin-collapse

collapse -- 默认重叠

discard -- 取消margin

separate -- 取消重叠

<img src="http://img.mukewang.com/585bc0e60001e49c12800720.jpg" alt="margin-collapse" title="margin-collapse" width="300"/>
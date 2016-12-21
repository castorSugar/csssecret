# padding
## padding 与元素的尺寸
### block

width非auto

影响尺寸

width:auto/box-sizing:border-box，并且padding不超大

不影响尺寸

### inline

影响***水平***方向尺寸，影响***背景颜色**

<img src="http://img.mukewang.com/585a8e290001326512800720.jpg" alt="背景颜色" title="背景颜色" width="300"/>

**高度可控分隔线**

	hello<span></span>world
	span{
		padding: 16px 6px 1px;
		margin-left: 12px;
		border-left: 2px solid;
		font-size: 0;
	}

<img src="http://img.mukewang.com/585a8e61000186f712800720.jpg" alt="高度可控分隔线" title="高度可控分隔线" width="300"/>


## 负值和百分比值

### 没有负值

### 百分比根据宽度计算

**实现正方形**

	padding: 50%

<img src="http://img.mukewang.com/585a8f9c0001368e12800720.jpg" alt="高实现正方形" title="实现正方形" width="300"/>

### inline

根据宽度计算

默认高度宽度细节有差异 -- 额外高度

垂直方向会让“幽灵空白节点”显现 -- strut出现
会换行

**padding断行**

<img src="http://img.mukewang.com/585a902e000145f512800720.jpg" alt="padding断行" title="padding断行" width="300"/>

**空inline元素+padding宽度也不等**

<img src="http://img.mukewang.com/585a90c400012b2112800720.jpg" alt="空inline元素" title="空inline元素" width="300"/>

## 标签元素内置padding

### ol/ul

元素内置padding-left，以px为单位不是em

字号很小，间距会很开

字号很大，序号移动到容器外


<img src="http://img.mukewang.com/585a91860001087812800720.jpg" alt="ol/ul" title="ol/ul" width="300"/>

设置心得

文字 12px~14px

ol/ul 22px~25px


### 表单元素

input textarea button select（ff,ie8+） -- 有

radio checkbox -- 无

<img src="http://img.mukewang.com/585a922b00018c6112800720.jpg" alt="表单元素内置padding" title="表单元素内置padding" width="300"/>

**button内置padding**

去除padding

chrome -- padding:0

firefox -- button::-moz-focus-inner{padding:0;}

<img src="http://img.mukewang.com/585a92700001361112800720.jpg" alt="chrome/firefox去除padding" title="chrome/firefox去除padding" width="300"/>

ie -- ie7文字越多越大

	button{overflow:visible;}

<img src="http://img.mukewang.com/585a932e0001eb9312800720.jpg" alt="ie去除padding" title="ie去除padding" width="300"/>


### padding与高度计算不兼容

ie7 firefox 不和规范

<img src="http://img.mukewang.com/585a94190001a4c612800720.jpg" alt="高度计算不兼容" title="高度计算不兼容" width="300"/>

解决方案

**a模拟**

**label实现**


<img src="http://img.mukewang.com/585a94560001165012800720.jpg" alt="解决方案" title="解决方案" width="300"/>

## padding与图形绘制

**三道杠**

<img src="http://img.mukewang.com/585a94e400011d4212800720.jpg" alt="三道杠" title="三道杠" width="300"/>

**环形空隙**

<img src="http://img.mukewang.com/585a95380001471012800720.jpg" alt="环形空隙" title="环形空隙" width="300"/>

## padding与布局

### 使用百分比单位构建固定比例布局

**1：1头图**

<img src="http://img.mukewang.com/585a95b70001d40012800720.jpg" alt="1：1头图" title="1：1头图" width="300"/>

### 配合margin等高布局

<img src="http://img.mukewang.com/585a95fe0001413212800720.jpg" alt="配合margin等高布局" title="配合margin等高布局" width="300"/>

### 两栏自适应布局

**容器上设置**

<img src="http://img.mukewang.com/585a964200016d0d12800720.jpg" alt="容器上设置" title="容器上设置" width="300"/>

**子容器上设置**

<img src="http://img.mukewang.com/585a9668000145d312800720.jpg" alt="子容器上设置" title="子容器上设置" width="300"/>

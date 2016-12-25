# relative
## relative、absolute和fixed
relative（老大）、absolute（老二）、fixed（老三）：**同源性**

老大对老二限制

1. 限制定位（老二在老大地盘内）
2. 限制层级（老大决定老二最大层级）
3. 限制overflow（老二超过老大地盘会被裁剪）

<img src="http://img.mukewang.com/585fd9430001824112800720.jpg" alt="老大对老二限制" title="老大对老二限制" width="300"/>

老大对老三限制

1. 限制层级（老大决定老三最大层级）

## relative定位

1. 是相对于自身的
2. 无侵入作用，即不会影响其他元素的布局

<img src="http://img.mukewang.com/585fdafc00018fb012800720.jpg" alt="无侵入作用" title="无侵入作用" width="300"/>

同时设置对立属性--top、bottom或者left、right

1. absolute表现为拉伸
2. relative表现为只有top和left生效

## relative层级

1. 提高层叠上下文

	页面有两张图片出现层叠情况，默认后一张图片层叠前一张，如果设置前一张图片position：relative，则前一张会层叠在前

2. 新建层叠上下文与层级控制

	父级设置了relative，限制子级的层级

	如果父元素的z-index：auto，就不会限制子级的层级，但是**不包括IE6/IE7**（因为IE6/IE7在z-index：auto情况下仍然会创建层叠上下文，不符合规范）

	<img src="http://img.mukewang.com/585fdbd100012ea012800720.jpg" alt="父元素的z-index：auto" title="父元素的z-index：auto" width="300"/>

## relative要遵循避免原则和最小化原则

1. 能不用relative则不用

	<img src="http://img.mukewang.com/585fdca7000161e512800720.jpg" alt="定位在左上角" title="定位在左上角" width="300"/>

2. absoluter定位不依赖

面对要定位到右边

relative作用的div范围越小越好

<img src="http://img.mukewang.com/585fdf050001f9cf12800720.jpg" alt="可以单独出来实现" title="可以单独出来实现" width="300"/>
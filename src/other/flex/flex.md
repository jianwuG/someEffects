### 容器属性
* flex-direction(项目的排列方向)
  * row | row-reverse | column | column-reverse;
* flex-wrap(如果一条轴线排不下，如何换行。)
  * flex-wrap: nowrap | wrap | wrap-reverse;
* flex-flow(flex-direction属性和flex-wrap属性的简写形式，默认值为row nowrap。)
* justify-content(定义了项目在主轴上的对齐方式。)
  * 定义了项目在主轴上的对齐方式。
* align-items(定义项目在交叉轴上如何对齐。)
  * flex-start | flex-end | center | baseline | stretch;
* align-content(多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用。)
  * flex-start | flex-end | center | space-between | space-around | stretch

### 项目属性
* order
  * 手动指定顺序
* flex-grow 
  * 放大
* flex-shrink
  * 缩小
* flex-basis
  * 定义了在分配多余空间之前，项目占据的主轴空间（main size）。浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为auto，即项目的本来大小。
* flex
  * 是flex-grow, flex-shrink 和 flex-basis的简写，默认值为0 1 auto。后两个属性可选。
* align-self
  * 允许单个项目有与其他项目不一样的对齐方式，可覆盖align-items属性


### flex(复合属性)
 * flex-grow 放大
   * 按一定比例去瓜分父div未分配的空间
   * 设置为1 自动填充剩余空间
 * flex-shrink 缩小 设置为0，即使窗口变小，该div也不会缩小
   * 某部分不想被压缩，设置为0
 * flex-basis






- [Flex 布局教程：语法篇](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)

- [Flex 布局教程：实例篇](http://www.ruanyifeng.com/blog/2015/07/flex-examples.html)

- [深入理解 flex-grow、flex-shrink、flex-basis](https://juejin.cn/post/6844904016439148551)
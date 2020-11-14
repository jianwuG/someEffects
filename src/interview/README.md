### 高频面试知识点总计
 * <a href="#1">盒子模型</a>
 * <a href="#2">margin塌陷和合并</a>
 * <a href="#3">居中方案</a>

#### <a name="#1">一、盒子模型</a>
描述：将html页面中的元素看做一个矩形的盒子，由内容(content)、内边距（padding）、边框（border）和外边距（margin）组成。
每个盒子除了有自己的大小和位置，还影响其他盒子的大小和文字
  * 分类
    *  W3c标准盒子模型（大小 = content + border + padding + margin）
    *  ie盒子模型（大小 = content + border + padding）
  * 语法
    * 不设置默认（内容长度=content + border + padding + margin）
    * box-sizing：content-box（内容长度=content）
    * box-sizing：border-box（内容长度=content  + padding + margin）
    * inherit（继承父）
  * 稳定性
    * width>padding>margin
    * 原因
     * margin外边距合并问题
     * padding影响盒子大小
     
     
   * 相关问题
     * padding-right或margin-right失效问题
       * 解决：设置box-sizing：border-box
     * margin合并和塌陷
     
#### <a name="#2">二、margin塌陷和合并</a>

塌陷问题描述： 在文档流中，父元素的高度默认是被子元素撑开的当子元素设置浮动之后，子元素会完全脱离文档流此时将会导致子元素
无法撑开父元素的高度，导致父元素高度塌陷

* 解决方案：
  * 隐藏属性bfc(块级格式化上下文，具有bfc等于隔离了独立容器)
    * 开启条件（满足任一条）：
      * 浮动元素 float：none除外
      * 绝对定位 position absolute fixed
      * display inline-blocks,table-cells,table-captions
      * overflow 为 hidden,auto,scroll
    * 特性
     * 阻止外边距折叠
     * 可以包含浮动的元素
     * 可以阻止元素被浮动元素覆盖
  * 给父元素设置边框
  
合并问题描述：处于上下位置关系的两个div容器，在通过margin-top、margin-bottom改变间距时，如果两个属性的值相同时，则两容器
间的距离就是这个值；如果两个属性的值不同，则取较大值作为两容器间的距离；

* 解决方案：
  * 调整最大值为目标值
  * 给两个容器外层添加overflow：hidden
  
  
#### <a name="#3">三、居中方案</a>
 * 水平居中
   * 行内元素
     * `text-align-center`
   * 块级元素
     * 一般居中方案  `margin:auto 0;`
     * 未知长度 ` position: absolute;
                    left: 50%;
                    transform: translate(-50%,0);`
     * 已知长度
       * 定位+margin-left ` position: absolute;
                width: 180px;
                left: 50%;
                margin-left: -90px`
       * 定位+margin ` position: absolute;
                width: 180px;
                left: 0;
                right: 0;
                margin: 0 auto`
                
     * flex ` display: flex;
                              justify-content: center;`

  
 * 垂直居中
   * 行内元素 `line-height 值为父元素 height 值`
   * 块级元素
     * table （未知高度）
     * 绝对定位
       * 未知高度 `position: absolute;
                   	top: 50%;
                   	transform: translate(0,-50%);`
                   	
       * 已知高度 
         * 定位+margin-top `position: absolute;
                              	top: 50%;
                              	margin-top: -30px;`
         *  定位+margin  `position: absolute;
                            	top: 0;
                            	bottom: 0;
                            	margin: auto 0`
                            	
     * flex  `  display: flex;
                       align-items: center;`

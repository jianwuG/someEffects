# 记录工作中常用的

* [1.超出文本...](text.html)

```
// 单行
p{
 width:300px;
 overflow:hidden;
 text-overflow:ellipsis;
 white-spece:nowrap;
}

//多行省略

p{
 width：300px；
  display: -webkit-box;
-webkit-box-orient: vertical;
 -webkit-line-clamp: 3;
overflow: hidden;
}




```

### 2.1.2 Ajax页面

```
    这里所说的“Ajax页面”是指，页面的文章内容是由Ajax获取并填充的，而非直接写入到HTML文档中。对这类页面的要求：页面的title默认为空，在Ajax内容获取后进行页面title的设置。

需要在上面获取的代码中mpid后面增加标记“&waitTitle=true”（形式如下）。
```

&lt;script id="\_trs\_ta\_js" src="//ta.8531.cn/c/js/ta.js?mpid=204&waitTitle=true" async="async" defer="defer"&gt;&lt;/script&gt;


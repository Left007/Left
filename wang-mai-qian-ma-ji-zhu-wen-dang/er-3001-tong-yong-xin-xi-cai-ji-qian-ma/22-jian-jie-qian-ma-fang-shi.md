## 2.2. 间接嵌码方式

间接嵌码，指的是通过Ajax或其他方式获取嵌码的字符串形式，然后通过jquery或zepto的append\(\)方法添加到页面上。

如果使用jquery插件的append\(\)方法，可以使用上面（[2.1直接嵌码](//wang-mai-qian-ma-ji-zhu-wen-dang/er-3001-tong-yong-xin-xi-cai-ji-qian-ma/21-zhi-jie-qian-ma-fang-shi.md#21-直接嵌码方式)）获取的嵌码。

由于zepto插件的问题，在使用append\(\)方法添加script标签时，不会请求src属性值所指向的文件，如果使用上面获取的嵌码，会导致ta.js不加载；而append\(\)添加script标签中的js代码可以执行，所以提供了下面的嵌码格式：

```
  <script>
    (function() {
        var ta = document.createElement("script");
        ta.id = "_trs_ta_js";
        ta.src = "//ta.8531.cn/c/js/ta.js?mpid=200";
        ta.setAttribute('async','async');
        ta.setAttribute('defer','defer');

        var s = document.getElementsByTagName("script")[0];
        s.parentNode.insertBefore(ta, s);
    })();
    </script>
```

只需要调整的ta.src的值，根据是否为Ajax页面\(2.1.2\)、是否为单页面应用\(2.1.3\)添加对应的标记。

由于代码比较多，所以应该仅在使用zepto进行间接嵌码时使用这种方式。

嵌码是非常关键的一步，影响到用户行为数据采集的准确性和完整性，特此提醒：


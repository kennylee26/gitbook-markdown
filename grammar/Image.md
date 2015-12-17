很明显地，要在纯文字应用中设计一个「自然」的语法来插入图片是有一定难度的。

Markdown 使用一种和链接很相似的语法来标记图片，同样也允许两种样式： <u>行内式(外链)</u>和<u>参考式</u>。

行内式(外链)的图片语法看起来像是：

```
![百度Logo](https://www.baidu.com/img/baidu_jgylogo3.gif)

![百度Logo](https://www.baidu.com/img/baidu_jgylogo3.gif "Optional title")
```

效果如下:

![百度Logo](https://www.baidu.com/img/baidu_jgylogo3.gif)

![百度Logo](https://www.baidu.com/img/baidu_jgylogo3.gif "Optional title")

详细叙述如下：

* 一个惊叹号 `!`
* 接着一个方括号，里面放上图片的替代文字
* 接着一个普通括号，里面放上图片的网址，最后还可以用引号包住并加上 选择性的 'title' 文字。

参考式(参考本地路径)的图片语法则长得像这样：

```
![Alt text][id]
```

「id」是图片参考的名称，图片参考的定义方式则和连结参考一样：

```
[id]: url/to/image  "Optional title attribute"
```

到目前为止， Markdown 还没有办法指定图片的宽高，如果你需要的话，你可以使用普通的 <img> 标签。



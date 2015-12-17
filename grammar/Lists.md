## Lists

Markdown 支持有序列表和无序列表。

无序列表使用星号、加号或是减号作为列表标记：

以下三者是等价的

```
*   Red
*   Green
*   Blue

+   Red
+   Green
+   Blue

-   Red
-   Green
-   Blue
```

以上代码会转成这样的HTML结果

```
<ul>
<li>Red</li>
<li>Green</li>
<li>Blue</li>
</ul>
```

而有序列表则使用数字接着一个英文句点：

```
1.  Bird
2.  McHale
3.  Parish
```

很重要的一点是，原始的数字标记并不会影响输出时的有序HTML结果，上面的列表所产生的 HTML 标记为：

```
<ol>
<li>Bird</li>
<li>McHale</li>
<li>Parish</li>
</ol>
```

列表项目标记通常是放在最左边，但是其实也可以缩进，最多 3 个空格，项目标记后面则一定要接着至少一个空格或制表符。

要让列表看起来更漂亮，你可以把内容用固定的缩进整理好：

```
*   Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
    Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
    viverra nec, fringilla in, laoreet vitae, risus.
*   Donec sit amet nisl. Aliquam semper ipsum sit amet velit.
    Suspendisse id sem consectetuer libero luctus adipiscing.
```

但是如果你懒，那也行：

```
*   Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
viverra nec, fringilla in, laoreet vitae, risus.
*   Donec sit amet nisl. Aliquam semper ipsum sit amet velit.
Suspendisse id sem consectetuer libero luctus adipiscing.
```

如果列表项目间用空行分开，在输出 HTML 时 Markdown 就会将项目内容用 <p> 标签包起来，举例来说：

```
*   Bird
*   Magic
```

会被转换为：
```
<ul>
<li>Bird</li>
<li>Magic</li>
</ul>
```

但是这个：

```
*   Bird

*   Magic
```

会被转换为：

```
<ul>
<li><p>Bird</p></li>
<li><p>Magic</p></li>
</ul>
```

列表项目可以包含多个段落，每个项目下的段落都必须缩进 4 个空格或是 1 个制表符：

```
1.  This is a list item with two paragraphs. Lorem ipsum dolor
    sit amet, consectetuer adipiscing elit. Aliquam hendrerit
    mi posuere lectus.

    Vestibulum enim wisi, viverra nec, fringilla in, laoreet
    vitae, risus. Donec sit amet nisl. Aliquam semper ipsum
    sit amet velit.

2.  Suspendisse id sem consectetuer libero luctus adipiscing.
```

如果你每行都有缩进，看起来会看好很多，当然，再次地，如果你很懒惰，Markdown 也允许：

```
*   This is a list item with two paragraphs.

    This is the second paragraph in the list item. You're
only required to indent the first line. Lorem ipsum dolor
sit amet, consectetuer adipiscing elit.

*   Another item in the same list.
```

显示效果如下：

1.  This is a list item with two paragraphs. Lorem ipsum dolor
    sit amet, consectetuer adipiscing elit. Aliquam hendrerit
    mi posuere lectus.

    Vestibulum enim wisi, viverra nec, fringilla in, laoreet
    vitae, risus. Donec sit amet nisl. Aliquam semper ipsum
    sit amet velit.

2.  Suspendisse id sem consectetuer libero luctus adipiscing.

如果要在列表项目内放进引用，那 `>` 就需要缩进：

```
*   A list item with a blockquote:

    > This is a blockquote
    > inside a list item.
```

显示效果如下:

*   A list item with a blockquote:

    > This is a blockquote
    > inside a list item.

如果要放代码区块的话，该区块就需要缩进(TAB)两次，也就是 8 个空格或是 2 个制表符：

```
*   一列表项包含一个列表区块：

        <代码写在这>
```

当然，如果段落首字母确实是数字开头，并且后面也是个英文句点的话，项目列表很可能会不小心产生，像是下面这样的一段话：

```
1986. What a great season.
```

换句话说，也就是在行首出现<u>数字-句点-空白</u>，要避免这样的状况，你可以在句点前面加上反斜杠进行转义。

```
1986\. What a great season.
```



和程序相关的写作或是标签语言原始码通常会有已经排版好的代码区块，通常这些区块我们并不希望它以一般段落文件的方式去排版，而是照原来的样子显示，Markdown 会用 `<pre>` 和 `<code>` 标签来把代码区块包起来。

## 代码块

### 区块

要在 Markdown 中建立代码区块很简单，有两种方法：

* 第一种，只要简单地缩进 4 个空格或是 1 个制表符就可以

* 第二种，在代码段落的头部和尾部用 <code>```</code> 包围起来（更建议用这种方式）。

例如，下面的输入：

<pre lang="no-highlight"><code>
这是一个普通段落：

    这是一个代码区块。 
    
这是一个普通段落：

```
这是一个代码区块。 
```         
</code></pre>

Markdown 都会转换成：

```
<p>这是一个普通段落：</p>

<pre><code>这是一个代码区块。
</code></pre>
```

而每行一阶的缩进（4 个空格或是 1 个制表符），都会被移除，例如：

```
Here is an example of AppleScript:

    tell application "Foo"
        beep
    end tell
```

会被转换为：


```
<p>Here is an example of AppleScript:</p>

<pre><code>tell application "Foo"
    beep
end tell
</code></pre>
```
   
一个代码区块会一直持续到没有缩进的那一行（或是文件结尾）。

在代码区块里面， `&` 、 `<` 和 `>` 会自动转成 HTML 实体，这样的方式让你非常容易使用 Markdown 插入范例用的 HTML 原始码，只需要复制贴上，再加上缩进就可以了，剩下的 Markdown 都会帮你处理，例如：

```
    <div class="footer">
        &copy; 2004 Foo Corporation
    </div>
```

会被转换为：

```
<pre><code>&lt;div class="footer"&gt;
    &amp;copy; 2004 Foo Corporation
&lt;/div&gt;
</code></pre>
```

### 行内代码块

在行内强大某些字符是代码块的话，可参考下面

	Inline `code` has `back-ticks around` it.

输出效果

Inline `code` has `back-ticks around` it.


## 代码块及高亮

代码块是Markdown内置语法之一，但是并不包含代码高亮。而`highlight`是Markdown常见插件之一，可实现目前大部分常见代码的高亮显示，大大提高代码可读性。想知道全部支持的语法名字参见 [highlight.js demo page](https://highlightjs.org/static/demo/).

可在用 <code>```</code> 包围的代码块头标明高亮的语法名字，参考下面例子:

<pre lang="no-highlight"><code>
```java
public abstract class L2Character extends L2Object {
  public static final Short ABNORMAL_EFFECT_BLEEDING = 0x0_0_0_1; // not sure

  public void moveTo(int x, int y, int z) {
    _ai = null;
    _log.warning("Should not be called");
    if (1 > 5) {
      return;
    }
  }

  /** Task of AI notification */
  @SuppressWarnings( { "nls", "unqualified-field-access", "boxing" })
  public class NotifyAITask implements Runnable {
    private final CtrlEvent _evt;

    List<String> mList = new ArrayList<String>()

    public void run() {
      try {
        getAI().notifyEvent(_evt, _evt.class, null);
      } catch (Throwable t) {
        t.printStackTrace();
      }
    }
  }
}
```

```javascript
var s = "JavaScript syntax highlighting";
alert(s);
```
 
```python
s = "Python syntax highlighting"
print s
```
 
```
No language indicated, so no syntax highlighting. 
But let's throw in a <b>tag</b>.
```
</code></pre>

效果

```java
public abstract class L2Character extends L2Object {
  public static final Short ABNORMAL_EFFECT_BLEEDING = 0x0_0_0_1; // not sure

  public void moveTo(int x, int y, int z) {
    _ai = null;
    _log.warning("Should not be called");
    if (1 > 5) {
      return;
    }
  }

  /** Task of AI notification */
  @SuppressWarnings( { "nls", "unqualified-field-access", "boxing" })
  public class NotifyAITask implements Runnable {
    private final CtrlEvent _evt;

    List<String> mList = new ArrayList<String>()

    public void run() {
      try {
        getAI().notifyEvent(_evt, _evt.class, null);
      } catch (Throwable t) {
        t.printStackTrace();
      }
    }
  }
}
```

```javascript
var s = "JavaScript syntax highlighting";
alert(s);
```
 
```python
s = "Python syntax highlighting"
print s
```
 
```
No language indicated, so no syntax highlighting. 
But let's throw in a <b>tag</b>.
```


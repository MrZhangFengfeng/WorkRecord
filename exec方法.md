#### 定义和用法
exec() 方法用于检索字符串中的正则表达式的匹配。
#### 语法
RegExpObject.exec(string)
#### 说明
> exec() 方法的功能非常强大，它是一个通用的方法，而且使用起来也比 test() 方法以及支持正则表达式的 String 对象的方法更为复杂。
如果 exec() 找到了匹配的文本，则返回一个结果数组。否则，返回 null。此数组的第 0 个元素是与正则表达式相匹配的文本，第 1 个元
素是与 RegExpObject 的第 1 个子表达式相匹配的文本（如果有的话），第 2 个元素是与 RegExpObject 的第 2 个子表达式相匹配的文
本（如果有的话），以此类推。除了数组元素和 length 属性之外，exec() 方法还返回两个属性。index 属性声明的是匹配文本的第一个字
符的位置。input 属性则存放的是被检索的字符串 string。我们可以看得出，在调用非全局的 RegExp 对象的 exec() 方法时，返回的数组
与调用方法 String.match() 返回的数组是相同的。
> 但是，当 RegExpObject 是一个全局正则表达式时，exec() 的行为就稍微复杂一些。它会在 RegExpObject 的 lastIndex 属性指定的字符
处开始检索字符串 string。当 exec() 找到了与表达式相匹配的文本时，在匹配后，它将把 RegExpObject 的 lastIndex 属性设置为匹配
文本的最后一个字符的下一个位置。这就是说，您可以通过反复调用 exec() 方法来遍历字符串中的所有匹配文本。当 exec() 再也找不到匹
配的文本时，它将返回 null，并把 lastIndex 属性重置为 0。

#### 实例
##### 在本例中，我们将全局检索字符串中的 W3School：

    <script type="text/javascript">

    var str = "Visit W3School"; 
    var patt = new RegExp("W3School","g");
    var result;

    while ((result = patt.exec(str)) != null)  {
      document.write(result);
      document.write("<br />");
      document.write(patt.lastIndex);
     }
    </script>
    
输出：

    W3School
    14
    
##### 使用 exec() 来检索字符串。

    <script type="text/javascript">
    var str = "Visit W3School, W3School is a place to study web technology."; 
    var patt = new RegExp("W3School","g");
    var result;

    while ((result = patt.exec(str)) != null)  {
      document.write(result);
      document.write("<br />");
      document.write(patt.lastIndex);
      document.write("<br />");
     }
    </script>

输出

    W3School
    14
    W3School
    24

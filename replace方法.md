#### 定义和用法
replace() 方法用于在字符串中用一些字符替换另一些字符，或替换一个与正则表达式匹配的子串。
#### 语法
stringObject.replace(regexp/substr,replacement)
#### 返回值
一个新的字符串

- - - 

### 实例
#### 例子 1
在本例中，我们将使用 "W3School" 替换字符串中的 "Microsoft"：
    <script type="text/javascript">

    var str="Visit Microsoft!"
    document.write(str.replace(/Microsoft/, "W3School"))

    </script>
输出：

    Visit W3School!

#### 例子 2
在本例中，我们将执行一次全局替换，每当 "Microsoft" 被找到，它就被替换为 "W3School"：

    <script type="text/javascript">

    var str="Welcome to Microsoft! "
    str=str + "We are proud to announce that Microsoft has "
    str=str + "one of the largest Web Developers sites in the world."

    document.write(str.replace(/Microsoft/g, "W3School"))

    </script> 
    
输出：

    Welcome to W3School! We are proud to announce that W3School
    has one of the largest Web Developers sites in the world.
    
#### 例子 3
您可以使用本例提供的代码来确保匹配字符串大写字符的正确：

    text = "javascript Tutorial";
    text.replace(/javascript/i, "JavaScript");
    
#### 例子 4

在本例中，我们将把 "Doe, John" 转换为 "John Doe" 的形式：

    name = "Doe, John";
    name.replace(/(\w+)\s*, \s*(\w+)/, "$2 $1");
    
#### 例子 5
在本例中，我们将把所有的花引号替换为直引号：

    name = '"a", "b"';
    name.replace(/"([^"]*)"/g, "'$1'");
    
#### 例子 6
在本例中，我们将把字符串中所有单词的首字母都转换为大写：

    name = 'aaa bbb ccc';
    uw=name.replace(/\b\w+\b/g, function(word){
      return word.substring(0,1).toUpperCase()+word.substring(1);}
      );
      

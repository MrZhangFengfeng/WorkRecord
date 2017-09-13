# HTML页面之间传递参数的方法

项目中经常会出现的一种情况，有一个列表，譬如是案例列表，点击列表中的某一项，跳转至详情页面。详情是根据所点击的某条记录生成的，因为案例和具体的详
情页面，都是用户后期自行添加的，我们开始编写时，不可能穷尽。因此跳转页面时，我们需要传递一个参数过去，这样我们才能通过这个参数进行数据请求，然后
根据后台返回的数据来生成页面。因此，通过`a`标签跳转的方式，肯定是行不通的。 

我们经常写`form`表单，提交时，可以传递参数，如果使用表单，并将其隐藏起来，应该可以达到效果。 
除此以外，`window.location.href`和`window.open`也可以达到效果。

- - -
## 一、通过form表单传递参数

    <form name = "frm" method = "get" action = "receive.html" onsubmit = "return foo()" style = "position:relative;">
        <input type="hidden"  name="arg" value = "" index = "lemon"> 
        <img class = "more" src = "main_jpg10.png" />
        <input type = "submit" />
    </form>
    
    <script>
        function foo(){
            var frm = window.event.srcElement;
            frm.arg.value = $(frm.arg).attr("index"); 
            return true;
        }
    </script>
    
点击图片时，跳转至receive.html页面。页面的url变成： 

    .../test/receive.html?arg=lemon

然后再对当前的url进行字符串分割 

    window.location.href.split("=")[1]//得到lemon 
    
我们拿到需要传来的参数之后，就可以根据这个进行下一步的处理了。 

- - -
## 二、通过`window.location.href`
譬如我们点击某个列表，需要传递一个字符串到detail.html页面，然后detail.html页面根据传来的值，通过ajax交互数据，加载页面的内容。

    let index = "lemon"; 
    let url = "receive.html?index="+index; 
    $("#more").click(function(){ window.location.href = url; });

当前页面会被替换成`recieve.html`的页面，页面的url变为： 

    .../test/receive.html?index=lemon

然后我们再用上面的方法提取自己需要的参数。

- - -
## 三、通过`window.open`

如果是希望打开一个新页面，而不是改变当前的页面，那么`window.location.href`就不适用了，此时，我们需要借助于`window.open()`来实现 

    <script>
        var index = "lemon";
        var url = "receive.html?index="+index;
        $("#more").click(function(){
            window.open(url)
        });
    </script>

这样在点击的时候，就会打开一个新页面，页面的url地址与上面相同。 

由于浏览器的安全限制，有些浏览器在弹出窗口配置方面增加限制，大多数浏览器都内置有弹出窗口的屏蔽程序，因此，弹出窗口有可能被屏
蔽，在弹出窗口被屏蔽时，需要考虑两种可能性，一种是浏览器内置的屏蔽程序阻止弹出窗口，那么 `window.open()`很可能返回`Null`，此时，
只要监测这个返回的值就可以确定弹出窗口是否被屏蔽。

另一种是浏览器扩展或其他程序阻止的弹出窗口，那么`window.open()`通常会抛出一个错误，因此，要像准确的检测弹出窗口是否被屏蔽，必
须在检测返回值的同时，将`window.open()`封装在`try-catch`块中,如下：

    <script>
        var blocked = false;
        try{
            var index = "lemon";
            var url = "receive.html?index="+index;
            $("#more").click(function(){
               var newWin = window.open(url);
               if(newWin == null){
                   blocked = true;
               }
            });
        } catch(ex){
            block = true;
        }
        if(blocked){
            alert("弹出窗口被阻止");
        }    
    </script>

- - -
# OVER

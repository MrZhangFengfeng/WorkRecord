## 需求：
- 输入框是随着内容的扩展而高度进行自动适应。
- 宽度不变。

- - -
### 第一种

    <style type="text/css">
    *{margin:0; padding:0;}
    .t{width:20em; font-size:12px; font-family:Arial, "宋体", sans-serif; line-height:25px; border:1px solid #09F; }
    .t pre{width:20em;font-family:Arial, "宋体", sans-serif; }
    pre{
    white-space:pre-wrap;
    white-space:-moz-pre-wrap;
    white-space:-pre-wrap;
    white-space:-o-pre-wrap;
    word-wrap:break-word;
    }
    .box{width:240px;margin:50px auto; padding:15px; background:#ccc; border:1px solid #bbb;}
    </style>

    <div class="box">
      <textarea id="t" class="t"  onkeyup="d()" style="height:25px; overflow:hidden"> </textarea>
    </div>
    
    <div class="t" id="d" style="visibility:hidden;"></div>
    <script language="javascript">
    function d(){
      var d = document.getElementById("d");
      var t = document.getElementById("t");
      var val = t.value;
      d.innerHTML ="<pre>" +val+" "+"</pre>";
      t.style.height = (d.offsetHeight-2) + "px";
      if(val == ""){
        t.value = " ";	
      }
    }
    </script>
    
- - -    
### 第二种(纯CSS，非真实textarea)

    <div style="border:1px solid #ccc;width:300px;min-height:30px" contentEditable="true"></div>

- - -
### 第三种(根据JS动态调整高度)

    <textarea name="textarea" id="textarea" style='overflow-y: hidden;height:20px' 
        onpropertychange="this.style.height = this.scrollHeight + 'px';
        " oninput="this.style.height = this.scrollHeight + 'px';">
        我是内容</textarea>
    <script>
        document.getElementById("textarea").style.height = 
          document.getElementById("textarea").scrollHeight + 10 + "px";
    </script>
    
- - -

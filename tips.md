### 从父级中继承方法： 直接super

     componentDidMount(){
            super.componentDidMount();       
        }   
        
- - -
### react没有ajax模块
- 他需要集成其他的JS库(eg.jquery/fetch/axios)来发送ajax请求。

- - -
### fetch.js
- 传统的ajax是指XMLHttpRequest(XHR)。
- fetch是新的发送ajax请求的方式，完全区别于XHR及其封装
- fetch的优点
     - 语法简洁，更加语义化
     - 基于标准promise实现(fetch(url)后得到的是promise，所以可以直接.then())
- 基本语法：

          fetch(url).then(response=>{
               responses.json().then(result=>{
                    //处理result
               })
          }).catch(e => {
               //异常处理
          })


- - -
### 一个#和三个###的区别
- a标签内 href="#",如果有滚动条点击之后会回到顶部去。
- a标签内 href="###"，如果有滚动条点击之后**不会**回到顶部去

- - -
### setState
定义为相同名字的时候可以直接setState，不用username：...;


     this.state={username="winter"}
     constant username = ...;
     this.setState({username})
          

- - -
### 遍历obj
     let obj ={1:"winter",2:"summer"}
- obj.1    //报错的
- obj.forEach(function(item){...})    //啥也log不出来
- for(item in obj){...}   //没问题  

所以当key值为number的时候  使用for in 来遍历。

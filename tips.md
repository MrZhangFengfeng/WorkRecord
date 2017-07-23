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
     - 基于标准promise实现
- 基本语法：

          fetch(url).then(response=>{
               responses.json().then(result=>{
                    //处理result
               })
          }).catch(e => {
               //异常处理
          })

- - - 

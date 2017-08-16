

### tofixed

toFixed() 方法可把 Number 四舍五入为指定小数位数的数字。

    NumberObject.toFixed(num)

num	必需。规定小数的位数，是 0 ~ 20 之间的值，包括 0 和 20，有些实现可以支持更大的数值范围。如果省略了该参数，将用 0 代替。
- - -
## But , there is a bug!

#### 今天被报bug 来找我说四舍五入有问题。

    1.55 =>1.5
    1.56 =>1.6

一看果真。原来是tofixed的问题。

所以看来还是得用我的老方法

    let num=0.066;
    num = Math.round(num*Math.pow(10,2))/Math.pow(10,2)
    console.log(num) //0.07
- - -
## 另外还有一个坑！

>  Math.round(num)    当里面的num达到千兆的时候可以  一旦达到万兆就会出现意想不到的错。
- - -
#### 和上面无关的一个随笔记录

    <a javascript:'fn()'>
    function fn(){
      alert("hello.")
    }

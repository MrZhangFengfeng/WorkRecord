### 在react中使用锚点跳转会导致location改变，发生路由错误。

解决方法：
在a标签内不写`href="#..."`，改为添加点击事件，在点击事件内使用：

- HTML5的scrollIntoView()
- 或者获取到目标元素 然后直接给focus

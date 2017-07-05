## WebKit浏览器CSS设置滚动条主要有下面7个属性:

- ::-webkit-scrollbar 滚动条整体部分，可以设置宽度啥的
- ::-webkit-scrollbar-button 滚动条两端的按钮
- ::-webkit-scrollbar-track 外层轨道
- ::-webkit-scrollbar-track-piece 内层轨道，滚动条中间部分（除去）
- ::-webkit-scrollbar-thumb 拖动条，滑块
- ::-webkit-scrollbar-corner 边角
- ::-webkit-resizer 定义右下角拖动块的样式

具体所指如下图:

![](imgs/webkit_scrollbar.png)

 上面是滚动条的主要设置属性，还有更详尽的CSS属性伪类，可以更丰富滚动条样式。

- :horizontal 水平方向的滚动条
- :vertical 垂直方向的滚动条
- :decrement 应用于按钮和内层轨道(track piece)。它用来指示按钮或者内层轨道是否会减小视窗的位置(比如，垂直滚动条的上面，水平滚动条的左边)
- :increment 和decrement类似，用来指示按钮或内层轨道是否会增大视窗的位置(比如，垂直滚动条的下面和水平滚动条的右边)
- :start 也应用于按钮和滑块。它用来定义对象是否放到滑块的前面。
- :end 类似于start伪类，标识对象是否放到滑块的后面。
- :double-button 该伪类以用于按钮和内层轨道。用于判断一个按钮是不是放在滚动条同一端的一对按钮中的一个。对于内层轨道来说，它表示内层轨道
是否紧靠一对按钮。
- :single-button 类似于double-button伪类。对按钮来说，它用于判断一个按钮是否自己独立的在滚动条的一段。对内层轨道来说，它表示内层轨道是否
紧靠一个single-button。
- :no-button 用于内层轨道，表示内层轨道是否要滚动到滚动条的终端，比如，滚动条两端没有按钮的时候。
- :corner-present 用于所有滚动条轨道，指示滚动条圆角是否显示。
- :window-inactive 用于所有的滚动条轨道，指示应用滚动条的某个页面容器(元素)是否当前被激活。(在webkit最近的版本中，该伪类也可以用于::selection
伪元素。webkit团队有计划扩展它并推动成为一个标准的伪类)

另外，**:enabled**、**:disabled**、**:hover** 和 **:active** 等伪类同样可以用于滚动条中。

- - -
### 一个demo
    /* 设置滚动条的样式 */
    ::-webkit-scrollbar {
        width: 12px;
    }

    /* 滚动槽 */
    ::-webkit-scrollbar-track {
        -webkit-box-shadow: inset 0 0 6px rgba(0,0,0,0.3);
        border-radius: 10px;
    }
    
    /* 滚动条滑块 */
    ::-webkit-scrollbar-thumb {
        border-radius: 10px;
        background: rgba(0,0,0,0.1);
        -webkit-box-shadow: inset 0 0 6px rgba(0,0,0,0.5);
    }
    ::-webkit-scrollbar-thumb:window-inactive {
        background: rgba(255,0,0,0.4);
    }
    
- - -

### IE下面CSS设置滚动条

IE下面就比较简单了，自定义的属性比较少，全是颜色。

- scrollbar-arrow-color: color; /三角箭头的颜色/
- scrollbar-face-color: color; /立体滚动条的颜色（包括箭头部分的背景色）/
- scrollbar-3dlight-color: color; /立体滚动条亮边的颜色/
- scrollbar-highlight-color: color; /滚动条的高亮颜色（左阴影？）/
- scrollbar-shadow-color: color; /立体滚动条阴影的颜色/
- scrollbar-darkshadow-color: color; /立体滚动条外阴影的颜色/
- scrollbar-track-color: color; /立体滚动条背景颜色/
- scrollbar-base-color:color; /滚动条的基色/

大概就这些，也可以定义cursor来定义滚动条的鼠标手势。

- - -
[一个兼容的滚动条解决方案]（http://lullabyus.iteye.com/blog/1314957）

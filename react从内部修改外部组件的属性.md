#### 今天遇到的一个问题，是在A组件内部来修改外部B组件的属性问题。

本来直接这样写：

    return children.map(function(child, index){
      child.props.format = format;
      return child;
    });

会报错：

    Uncaught TypeError: Cannot assign to read only property 'format' of object '#<Object>'
    
接下里这样进行修改。相当于new一个副本出来  最后再用这个副本替换原先的样本。

    return children.map(function(child, index){
        let newChild = {...child};
        newChild.props = {...child.props};
        newChild.props.format = format;
        child = newChild;
        return child;
    });

这样就可以了，此法不失为一个good idea。

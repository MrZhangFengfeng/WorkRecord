## jQuery 中 attr() 和 prop() 方法的区别

JQuery官方建议：具有 true 和 false 两个属性的属性，如 checked, selected 或者 disabled 使用prop()，其他的使用 attr()。

- - -
看JQuery源码内：

attr() 里面，最关键的两行代码

    elem.setAttribute( name, value + "" ); 
    ret =  elem.getAttribute( name );
    
很明显的看出来，使用的 DOM 的 API setAttribute() 和 getAttribute() 方法操作的属性元素节点。

prop() 里面，最关键的两行代码

    return ( elem[ name ] = value );
    return elem[ name ];

可以理解为 `document.getElementById(el)[name] = value`，这是转化成 element 的一个属性。

- - -
于是发现，二者返回的不一样了。

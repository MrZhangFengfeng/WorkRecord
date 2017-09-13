## 兄弟组件之间通信方式

- PubSub.js
- 方法写在他们共同继承的一个组件里
- 在`兄弟组件A`中写 静态方法，然后在`兄弟组件B`中用`类名.方法`名来调用

- - -

## 组件包含
在UILink内的render方法中加上`{this.props.children}`

    <UILink value={i18n.winter} >
              <UIBadges>5</UIBadges>
     </UILink>
 
 - - -
 ## 本地用着玩
 
    npm i http-server -g
 
 - - -
- 数据不停的在变，在`componentDidMount()`里设置定时器

- 工具`Markman` --> PSD图的标注

- 如果元素有透明的背景，则需要存储为`PNG24`的格式。

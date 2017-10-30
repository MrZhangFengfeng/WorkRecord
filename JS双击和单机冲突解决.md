## JS双击和单机冲突解决.md

    <div onDoubleClick ={this.OnDoubleClick.bind(this)} onClick = {this.onClick.bind(this,arg)} />

在单击内设置`setTimeout`
    
    onClick(arg) {
        clearTimeout(this.timer)
        let self = this;
        this.timer = setTimeout(function() {
             self.props.onClick(arg);
        },200) 
    }

    OnDoubleClick() {
        clearTimeout(this.timer)
        this.props.OnDoubleClick();
    }

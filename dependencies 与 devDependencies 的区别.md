## dependencies 与 devDependencies 的区别

npm install 在安装 npm 包时，有两种命令参数可以把它们的信息写入 package.json 文件：

    –save
    –save-dev
    
在它的文档里，有一个小区别，--save 会把依赖包名称添加到 package.json 文件 dependencies 键下，
--save-dev 则添加到 package.json 文件 devDependencies 键下，譬如：

    {
      "name": "yo",
      "version": "0.0.0",
      "dependencies": {},
      "devDependencies": {
        "grunt": "~0.4.1",
        "grunt-contrib-copy": "~0.4.1",
        "grunt-contrib-concat": "~0.3.0",
        "grunt-contrib-uglify": "~0.2.0",
        "grunt-contrib-compass": "~0.7.0",
        "grunt-contrib-jshint": "~0.7.0",
        "grunt-contrib-cssmin": "~0.7.0",
      }
    }
    
不过这只是它们的表面区别。它们真正的区别是，devDependencies 下列出的模块，是我们开发时用的，
比如 grunt-contrib-uglify，我们用它混淆 js 文件，它们不会被部署到生产环境。dependencies 下
的模块，则是我们生产环境中需要的依赖。



### 开发环境，测试环境和生产环境

- 开发环境：开发环境是程序猿们专门用于开发的服务器，配置可以比较随意， 为了开发调试方便，一般打开全部错误报告。

- 测试环境：一般是克隆一份生产环境的配置，一个程序在测试环境工作不正常，那么肯定不能把它发布到生产机上。

- 生产环境：是值正式提供对外服务的，一般会关掉错误报告，打开错误日志。

三个环境也可以说是系统开发的三个阶段：**开发->测试->上线**，其中生产环境也就是通常说的真实环境。

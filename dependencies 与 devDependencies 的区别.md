## dependencies 与 devDependencies 的区别

npm install 在安装 npm 包时，有两种命令参数可以把它们的信息写入 package.json 文件：

    –save
    –save-dev
    
但它的文档里1，只提到一个小区别，--save 会把依赖包名称添加到 package.json 文件 dependencies 键下，
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



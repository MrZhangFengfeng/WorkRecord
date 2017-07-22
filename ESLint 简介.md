## ESLint是一个QA工具，用来避免低级错误和统一代码的风格。

### ESLint被设计为完全可配置的，主要有两种方式来配置ESLint：

- 在注释中配置：使用JavaScript注释直接把配置嵌入到JS文件中。
- 配置文件：使用下面任一的文件来为全部的目录和它的子目录指定配置信息。
- javascript：使用.eslintrc.js文件并导出一个包含配置的对象。
- YAML：.eslintrc.yaml或者.eslintrc.yml
- JSON：.eslintrc.json，并且此文件允许使用JS形式的注释
- 废弃的用法：.eslintrc，此文件可以是JSON或者YAML
- package.json：在package.json文件中创建eslintConfig属性，所有的配置包含在此属性中。

这些文件的优先级则是按照以上出现的顺序（.eslintrc.js > .eslintrc.yaml > .eslintrc.yml > .eslintrc.json > .eslintrc > package.json）。

### 可以被配置的信息主要分为3类：

- Environments：你的 javascript 脚步将要运行在什么环境（如：nodejs，browser，commonjs等）中。
- Globals：执行代码时脚步需要访问的额外全局变量。
- Rules：开启某些规则，也可以设置规则的等级。

### 安装

      npm install -g eslint
    
### 用方法

如果你的项目还没有配置文件的话，可以通过指定--init参数来生成一个新的配置文件：

    eslint --init
    
然后，配合命令行的eslint工具就可以检查代码了。

    eslint [options] file.js [file.js] [dir]
    
当然，也可以安装在项目中，然后配合编辑器的插件（如vscode-eslint）来使用。

### 配置

指定全局变量
可以在配置文件或注释中指定额外的全局变量，false表明变量只读：

注释：
/* global var1, var2 */
/* global var1:false, var2:false */

    JSON：
    {
      "globals": {
          "var1": true,
          "var2": false
      }
    }
    
### 规则

在配置文件中可以设置一些规则。
#### 规则的错误等级有三种：

- "off" 或者 0：关闭规则。
- "warn" 或者 1：打开规则，并且作为一个警告（不影响exit code）。
- "error" 或者 2：打开规则，并且作为一个错误（exit code将会是1）。


      /* eslint eqeqeq: "off", curly: "error" */
      /* eslint eqeqeq: 0, curly: 2 */


#### 也可以在注释中关闭所有或者某个规则：

    /* eslint-disable */
    /* eslint-enable */

    /* eslint-disable no-alert, no-console */
    /* eslint-enable no-alert, no-console */
    
具体的规则可以在官网上找到，或者使用别人写好的配置，例如[eslint-config-airbnb](https://www.npmjs.com/package/eslint-config-airbnb)。

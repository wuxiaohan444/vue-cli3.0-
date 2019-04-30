#vue-cli3.0中使用postcss-poxtorem

##1·创建rem.js文件，创建一个utils文件夹，把rem.js放入文件夹中

```javascript
_// 基准大小
****const baseSize = 32
// 设置 rem 函数
function setRem () {
  // 当前页面宽度相对于 750 宽的缩放比例，可根据自己需要修改。
  const scale = document.documentElement.clientWidth / 750
  // 设置页面根节点字体大小
  document.documentElement.style.fontSize = (baseSize * Math.min(scale, 2)) + 'px'
}
// 初始化
setRem()
// 改变窗口大小时重新设置 rem
window.onresize = function () {
  setRem()
}_****
```

##2.在main.js中引入rem.js

```
import './utils/rem'
```

##3.配置 postcss-pxtorem 自动转换px为rem
###1.安装 postcss-pxtorem
$ npm install postcss-pxtorem -D
###在根目录下创建 vue.config.js配置postcss-pxtorem

```javascript
module.exports = {
    lintOnSave: true,
    css: {
        loaderOptions: {
            postcss: {
                plugins: [
                    require('postcss-pxtorem')({
                        rootValue : 32, // 换算的基数
                        selectorBlackList  : ['weui','mu'], // 忽略转换正则匹配项
                        propList   : ['*'],
                    }),
                ]
            }
        }
    },
}

```

按照上述配置项目后，即可在开发中直接使用 px 单位开发。


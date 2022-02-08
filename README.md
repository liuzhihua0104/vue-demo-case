# vue-demo-case

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).


### 如何用脚手架搭建项目，如何配置
[原文地址](https://www.cnblogs.com/coober/p/10875647.html)
https://www.cnblogs.com/coober/p/10875647.html

### 项目中引入rem
1. 安装：
cnpm install lib-flexible postcss-plugin-px2rem --save-dev

2. 配置rem：
在main.js 文件中导入： import "lib-flexible/flexible";
rem 就可以生效了，项目中我们正常写px会自动帮我们转换为rem

3. 配置px—>rem:
创建vue.config.js文件
```
 module.exports = {
  // rem适配
  css: {
    loaderOptions: {
      postcss: {
        plugins: [
          require('postcss-plugin-px2rem')({
            rootValue: 75, //换算基数， 默认100  ，这样的话把根标签的字体规定为1rem为50px,这样就可以从设计稿上量出多少个px直接在代码中写多上px了。
            // unitPrecision: 5, //允许REM单位增长到的十进制数字。
            //propWhiteList: [],  //默认值是一个空数组，这意味着禁用白名单并启用所有属性。
            // propBlackList: [], //黑名单
            // exclude: /(page_pc)/i,  //默认false，可以（reg）利用正则表达式排除某些文件夹的方法，例如/(node_module)/ 。如果想把前端UI框架内的px也转换成rem，请把此属性设为默认值
            exclude: /node_modules/i,
            // selectorBlackList: ['van-'], //要忽略并保留为px的选择器,我们一般不转换vantui中的大小
            // ignoreIdentifier: false,  //（boolean/string）忽略单个属性的方法，启用ignoreidentifier后，replace将自动设置为true。
            // replace: true, // （布尔值）替换包含REM的规则，而不是添加回退。
            mediaQuery: false,  //（布尔值）允许在媒体查询中转换px。
            minPixelValue: 3 //设置要替换的最小像素值(3px会被转rem)。 默认 0
          }),
        ]
      }
    }
  },
}
```

[原文地址](https://blog.csdn.net/weixin_45819748/article/details/111991269) 
https://blog.csdn.net/weixin_45819748/article/details/111991269




### demo
1、vue-dragable 拖拽
[官网教程](https://www.itxst.com/vue-draggable/fueijmfy.html)
https://www.itxst.com/vue-draggable/fueijmfy.html

### 大转盘
[大转盘样式原文地址](https://blog.csdn.net/lgno2/article/details/111771997) 
https://blog.csdn.net/lgno2/article/details/111771997


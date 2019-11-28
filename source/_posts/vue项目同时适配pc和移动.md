---
title: vue项目同时适配pc和移动
date: 2019-11-28 19:57:44
tags:
- vue
categories: 
- vue
---

# vue项目同时适配pc和移动

先安装 `lib-flexible` 和 `px2rem-exclude`

> npm i lib-flexible px2rem-exclude

<!--more-->

## 移动端

package.json

```
"postcss": {
  "plugins": {
    "autoprefixer": {},
    "px2rem-exclude": {
      "remUnit": 37.5,
      "exclude": "node_modules|home"  // 忽略某些目录
    }
  }
}
```

或者 postcss.config.js

```
plugins: {
  autoprefixer: {},
  'px2rem-exclude': {
    'remUnit': 75,
    'exclude': /node_modules|pc/i  // 忽略某些目录
  }
}
```

## PC端

APP.vue(暂时只想到这种办法)

```
mounted () {
  if (this.$util.browserDetection() === 'PC') {
    let that = this
    this.setRemFontSize()
    window.addEventListener('resize', function () {
      setTimeout(() => {
        that.setRemFontSize()
      }, 1000)
    })
  }
},
methods: {
  setRemFontSize () {
    let remSize = window.innerWidth / 19.2
    document.querySelector('html').style.fontSize = remSize + 'px'
  }
}
```

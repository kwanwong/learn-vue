## Vue 2.0学习笔记
---
### 声明式渲染
> Vue.js的核心是一个允许采用简洁的模板语法来声明式的将数据渲染进DOM:

*HTML:*

```html
    <div id="app">
        {{ message }}
    </div>
```
*JS:*

```js
    var app = new Vue({
        el: '#app',
        data: {
            message: 'Hello Vue!'
        }
    })
```  
*输出:*
> Hello Vue! 
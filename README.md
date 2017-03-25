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

### v-bind:class
> 为元素绑定样式，可简写为:class

*第一种写法:*

```html
//当row.is_completed为true时，为当前div追加样式.completed
<div class="row" v-bind:class="{'completed': row.is_completed}"></div>
```

*第二种写法*

```html
//可使用三元运算符
<div v-bind:class="['row', row.is_completed ? 'completed' : 'undo']"></div>
```

### computed
> 对于复杂的逻辑，使用表达式计算以后输出结果

*例子:*

```html
<div id="example">
    <p>原始字符串: {{ message }}</p>
    <p>翻转字符串: {{ reversedMessage }}</p>
</div>
```

```js
var vm = new Vue({
    el: '#example',
    data: {
        message: 'Hello'
    },
    computed: {
        reversedMessage: function(){
            return this.message.split('').reverse().join('');
        }
    }
})
```
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

### 样式绑定v-bind:class
> 为元素绑定样式，可简写为:class

*第一种写法:*
当row.is_completed为true时，为当前div追加样式.completed
```html
<div class="row" v-bind:class="{'completed': row.is_completed}"></div>
```

*第二种写法*
可使用三元运算符
```html
<div v-bind:class="['row', row.is_completed ? 'completed' : 'undo']"></div>
```

### 属性计算computed
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

### 组件化应用
> 组件系统是一种抽象，允许我们使用小型，自包含和通常可复用的组件构建大型应用

```js
Vue.component('todo-item', {
    template: '#todo-item-template',
    props: ['lists'],
    data: function(){
        return {
            title: '标题'
        }
    }
})

new Vue({
    el: '#app',
    data: {
        todos:[
            
        ]
    }
})
```

```html
<script type="text/x-template" id="todo-item-template">
<ul class="list-group">
    <li class="list-group-item" v-for="item in items">{{ item.title }}</li>
</ul>
</script>
```

*调用:*
```html
<todo-item :lists="todos"></todo-item>
```
###Vue 2.0学习笔记
####声明式渲染
Vue.js的核心是一个允许采用简洁的模板语法来声明式的将数据渲染进DOM:

`HTML:`

    <div id="app">
        {{ message }}
    </div>

`JS:`

    var app = new Vue({
        el: '#app',
        data: {
            message: 'Hello World'
        }
    })
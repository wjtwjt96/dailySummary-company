#### Vue入门

##### 1. 基本语法

Vu实例定义：

```javascript
<div id="app">
  {{ message }}
</div>
//vue实例
var app = new Vue({
  el: '#app', //组件id
  data: {  //数据
    message: '你好，第一次使用'
  }
});

```

- 获取vue实例的值：{{ 数据名 }}

- vue属性绑定：**v-bind：属性名** = ”数据名"

  ```javascript
  <div id="app-2">
    <span v-bind:title="message">
      鼠标悬停几秒钟查看此处动态绑定的提示信息！
    </span>
  </div>
  
  var app2 = new Vue({
    el: '#app-2',
    data: {
      message: '页面加载于 ' + new Date().toLocaleString()
    }
  })
  ```

- vue条件判断：**v-if = "数据名"**

  ```javascript
  <div id="app-3">
    <p v-if="seen">现在你看到我了</p>
  </div>
  
  var app3 = new Vue({
    el: '#app-3',
    data: {
      seen: true
    }
  })
  ```

- vue循环：**v-for = "id(字段名) in ids(数据名)"**

  ```javascript
  <div id="app-4">
    <ol>
      <li v-for="todo in todos">
        {{ todo.text }}
      </li>
    </ol>
  </div>
  
  var app4 = new Vue({
    el: '#app-4',
    data: {
      todos: [
        { text: '学习 JavaScript' },
        { text: '学习 Vue' },
        { text: '整个牛项目' }
      ]
    }
  })
  
  ```

- vue事件绑定：**v-on :事件名**=“方法名”

  ```javascript
  div id="app-5">
    <p>{{ message }}</p>
    <button v-on:click="reverseMessage">反转消息</button>
  </div>
  
  var app5 = new Vue({
    el: '#app-5',
    data: {
      message: 'Hello Vue.js!'
    },
    methods: {
      reverseMessage: function () {
        this.message = this.message.split('').reverse().join('')
      }
    }
  })
  ```

- vue `v-model` 指令，它能轻松实现表单输入和应用状态之间的双向绑定

  ```javascript
  <div id="app-6">
    <p>{{ message }}</p>
    <input v-model="message">
  </div>
  
  var app6 = new Vue({
    el: '#app-6',
    data: {
      message: 'Hello Vue!'
    }
  })
  ```


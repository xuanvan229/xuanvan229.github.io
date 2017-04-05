<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <span v-bind:title="msg">
      Hover your mouse over me for a few second
    </span>
    <p v-if="seen">Now you see me</p>
    <ul>
      <li v-for="todo in todos">
       {{ todo.text }}
     </li>
    </ul>
    <p>{{messenge}}</p>
    <input v-model="messenge">
    <button v-on:click="reverseMessage">ReversaMessage</button>
    <div id="app-7">
      <ol>
        <todo-item v-for="item in groceryList" v-bind:todo="item"></todo-item>
      </ol>
    </div>
  </div>

</template>

<script>
import Vue from 'vue'
Vue.component('todo-item', {
  props: ['todo'],
  template: '<li>{{ todo.text }}</li>'
})
export default {
  name: 'hello',
  data () {
    return {
      msg: 'Hello Xuan, Wellcome to your Vuejs App ' + new Date(),
      seen: true,
      todos: [
         { text: 'Learn JavaScript' },
         { text: 'Learn Vue' },
         { text: 'Build something awesome' },
         {text: 'ReactJs'}
      ],
      messenge: 'Hello Vuejs!',
      groceryList: [
        { text: 'Vegetables' },
        { text: 'Cheese' },
        { text: 'Whatever else humans are supposed to eat' }
      ]
    }
  },
  methods: {
    reverseMessage: function () {
      this.messenge = this.messenge.split('').reverse().join('')
    }

  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>

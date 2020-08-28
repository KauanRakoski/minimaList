<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Hello world"/>
    <Todos v-on:del-todo="deleteTodo" v-bind:todos="todos"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Todos from './components/Todos.vue'
export default {
  name: 'App',
  components: {
    HelloWorld,
    Todos
  },
  data() {
    return{
      todos: [{
        id: 1,
        title: "Poop",
        completed: false
      }]
    }
  },
  methods: {
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id !== id);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

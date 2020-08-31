<template>
  <div id="app">
    <Header/>
    <HelloWorld msg="Add a todo:"/>
    <Add v-on:add-todo="addTodo" />
    <Todos v-on:del-todo="deleteTodo" v-bind:todos="todos"/>
  </div>
</template>

<script>
  import HelloWorld from './components/HelloWorld.vue';
  import Todos from './components/Todos.vue';
  import Add from './components/Add.vue';
  import Header from './components/layout/Header'

  export default {
    name: 'App',
    components: {
      HelloWorld,
      Todos,
      Add,
      Header
    },
    data() {
      return{
        todos: []
      }
    },
    methods: {
      deleteTodo(id){
        this.todos = this.todos.filter(todo => todo.id !== id);
      },
      addTodo(newTodo){
        this.todos = [...this.todos, newTodo]
      }
    }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }
</style>

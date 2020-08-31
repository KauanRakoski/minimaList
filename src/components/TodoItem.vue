<template>
    <div class="p-2 my-2 w-50 d-flex justify-content-between align-items-center rounded border" v-bind:class="{'text-muted': todo.completed}">
        <div class="p-2">
        <input  class="mr-2 my-0" type="checkbox" v-on:change="markComplete">
        <label class="h4">{{todo.title}}</label>
        </div>
        <button @click="$emit('del-todo', todo.id)" class="btn btn-danger">X</button>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markComplete(){
            this.todo.completed = !this.todo.completed;
        }
    }
}
</script>

<style scoped>
    .is-completed{
        text-decoration: line-through;
        color: gray;
    }
</style>
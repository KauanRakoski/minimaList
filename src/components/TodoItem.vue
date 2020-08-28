<template>
    <div v-bind:class="{'is-completed': todo.completed}">
        <input type="checkbox" v-on:change="markComplete">
        <label>{{todo.title}}</label>
        <button @click="$emit('del-todo', todo.id)" class="del">X</button>
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
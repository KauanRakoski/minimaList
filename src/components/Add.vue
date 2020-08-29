<template>
    <form @submit="AddTodo">
        <input type="text" v-model="title">
        <input type="submit" value="Submit">
    </form>
</template>

<script>
    import {v4} from 'uuid';
    export default {
        name: "Add",
        data(){
            return {
                title: "",
                
            }
        },
        methods: {
            AddTodo(e){
                e.preventDefault();
                const newTodo = {
                    id: v4(),
                    title: this.title,
                    completed: false
                }
                this.$emit("add-todo", newTodo);

                this.title = ''
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>
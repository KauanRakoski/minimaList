<template>
    <form @submit="AddTodo" class="form-inline my-2 my-lg-0 w-100 d-flex justify-content-center">
      <input maxlength="20" class="form-control mr-sm-1" type="search" placeholder="Search" v-model="title" aria-label="Search">
      <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Save</button>
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


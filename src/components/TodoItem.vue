<template>
    <!-- apply is-complete style if todo.completed is true -->
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <!-- v-on to add event listener -->
        <input type="checkbox" v-on:change="markComplete" />
        <p>{{todo.title}}</p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        // toggle the checkbox
        markComplete(){
            this.todo.completed = !this.todo.completed;
        }
    }
}
</script>

<style scoped>
    .todo-item{
        background-color: #a7ce9e;
        padding: 10px;
        border-bottom: 1px white dotted;
        display: flex;
    }

    .todo-item input{
        margin-right: 5px;
    }

    .is-complete{
        text-decoration: line-through;
    }
</style>
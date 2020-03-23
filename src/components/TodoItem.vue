<template>
    <!-- apply is-complete style if todo.completed is true -->
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <p>{{todo.title}}</p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"]
}
</script>

<style scoped>
    .todo-item{
        background-color: #a7ce9e;
        padding: 10px;
        border-bottom: 1px white dotted;
    }

    .is-complete{
        text-decoration: line-through;
    }
</style>
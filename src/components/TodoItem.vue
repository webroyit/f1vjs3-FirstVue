<template>
    <div class="todo-item">
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
</style>
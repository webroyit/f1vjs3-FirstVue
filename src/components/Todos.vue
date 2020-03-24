<template>
    <div>
        <!-- v-bind to add key -->
        <!-- v-for to loop through array  -->
        <div v-bind:key="todo.id" v-for="todo in todos">
            <!-- v-on get the child component event -->
            <!-- $emit to pass a method or value -->
            <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)" />
        </div>
    </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";

export default {
    name: "Todos",
    components: {
        TodoItem
    },
    // get the data from another component
    props: ["todos"]
}
</script>

<style lang="stylus" scoped>

</style>
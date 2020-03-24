<template>
    <!-- apply is-complete style if todo.completed is true -->
    <div class="todo-item">
        <div class="item" v-bind:class="{'is-complete':todo.completed}">
            <!-- v-on to add event listener -->
            <input type="checkbox" v-on:change="markComplete" />
            <p>{{todo.title}}</p>
        </div>
        <!-- @click for click handler -->
        <!-- $emit() for event -->
        <button @click="$emit('del-todo', todo.id)" class="delete">x</button>
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
        justify-content: space-between;
    }

    .todo-item input{
        margin-right: 5px;
    }

    .item{
        display: flex;
        align-items: center;
    }

    .is-complete{
        text-decoration: line-through;
    }

    .delete{
        padding: 4px 8px;
        color: white;
        background-color: #aa1c1c;
        cursor: pointer;
    }
</style>
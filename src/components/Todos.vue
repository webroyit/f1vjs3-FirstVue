<template>
    <div>
        <!-- v-bind to add key -->
        <!-- v-for to loop through array  -->
        <div v-bind:key="todo.id" v-for="todo in todos">
            <h3>{{todo.title}}</h3>
        </div>
    </div>
</template>

<script>
export default {
    name: "Todos",
    // get the data from another component
    props: ["todos"]
}
</script>

<style lang="stylus" scoped>

</style>
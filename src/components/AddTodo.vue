<template>
    <div>
        <form>
            <!-- v-model to create two way data binding -->
            <input type="text" v-model="title" name="title" placeholder="Add what to do" />
            <input type="submit" value="Add" class="btn" />
        </form>
    </div>
</template>

<script>
export default {
    name: "AddTodo",
    data(){
        return{
            title: ""
        }
    }
}
</script>

<style scoped>
    form{
        display: flex;
    }

    input[type="text"] {
        flex: 10;
        padding: 5px;
    }

    input[type="submit"] {
        flex: 2;
    }
</style>
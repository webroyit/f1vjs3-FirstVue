<template>
    <div>
        <form>
            <input type="text" name="title" placeholder="Add what to do" />
            <input type="submit" value="Add" class="btn" />
        </form>
    </div>
</template>

<script>
export default {
    name: "AddTodo"
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
<template>
    <div>
        <!-- @submit fire the method when the button is clicked -->
        <form @submit="addTodo">
            <!-- v-model to create two way data binding -->
            <input type="text" v-model="title" name="title" placeholder="Add what to do" />
            <input type="submit" value="Add" class="btn" />
        </form>
    </div>
</template>

<script>
import { v4 as uuidv4} from "uuid";

export default {
    name: "AddTodo",
    data(){
        return{
            title: ""
        }
    },
    methods:{
        // create todo object
        addTodo(e){
            // prevent the page from reloading
            e.preventDefault();

            const newTodo = {
                // generate random id
                id: uuidv4(),
                title: this.title,
                completed: false
            }

            // pass them to the parent component
            this.$emit("add-todo", newTodo);

            // reset the input
            this.title = "";
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
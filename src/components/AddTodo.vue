<template>
    <div>
        <form @submit.prevent="addTodo">
            <input type="text" v-model="title" name="title" placeholder="Add todo..."  autocomplete="off">
            <input type="submit" value="Submit" class="btn">
        </form>
    </div>
</template>
<script>
import { v4 as uuidv4 } from 'uuid'
export default {
    name: "AddTodo",
    data(){
        return{
            title: ''
        }
    },
    methods: {
        addTodo(){
            // e.preventDefault();
            
            const newTodo = {
                id: uuidv4(),
                title: this.title,
                completed: false
            }
            this.$emit('add-todo', newTodo)
            this.title = ''
        }
    }
}
</script>
<style scoped>
    form{
        margin: 0 auto;
        width: 340px;
        height: 50px;
        display:flex;
    }
    input[type="text"]{
        flex: 10;
        padding-left: 20px;
        border: 3px #fff3a9 solid;
        border-radius: 0 0 0 5px;
        transition: all .3s ease;
    }
    input:focus{
        outline:none;
        border: 3px #f5df4d solid;
    }
    .btn{
        cursor: pointer;
        font-weight: bold;
        background-color: #fff3a9;
        color: #333;
        border: none;
        border-radius: 0 0 5px 0;
        flex:2;
        font-family: Arial, Helvetica, sans-serif;
        transition: all .3s ease;
    }
    .btn:hover{
        background: #f5df4d;
    }
</style>
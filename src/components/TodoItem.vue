<template>
    <div class="todo-item" v-bind:class="{'is-completed':todo.completed}">
       <p>
           <span class="todo-checkbox">
                <input type="checkbox" v-on:change="markComplete">
           </span>      
           {{todo.title}}
           <button @click="$emit('del-todo', todo.id)" class="del">
               <font-awesome-icon icon="trash-alt" />
           </button>
        </p> 
    </div>
</template>
<script>

export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markComplete (){
            this.todo.completed = !this.todo.completed
        }
    }
}
</script>
<style scoped>
    .todo-item{
        width: 300px;
        background-color: #f1f1f1;
        padding:10px 20px;
        border-bottom: 7px dotted #f5df4d;       
        border-radius: 5px;
        font-family: Arial, Helvetica, sans-serif;
    }
    .is-completed {
        text-decoration: line-through;
    }
    .del{
        width: 30px;
        height: 30px;
        float: right;
        background-color: #998456;
        color: #f0f0f0;
        border: none;
        border-radius: 50%;
    }
    .del:hover{
        cursor: pointer;
    }
    .todo-checkbox{
        cursor: pointer;
    }
    .todo-checkbox input{
        cursor: pointer;
    }
</style>
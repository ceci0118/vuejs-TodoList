<template>
    <div class="header">
        <h1 class="title">Todo List</h1>
    </div>
</template>
<script>
export default {
    name: "Header"
}
</script>
<style scoped>
    .header{
        width: 300px;
        height: 60px;
        padding: 20px;
        background-color: #333;
        color: #fff;
        margin: 0 auto;
        border-radius: 5px 5px 0 0;
    }
    .title{
        text-align: center;
        margin: auto 0;
        font-size: 3em;
        font-family: Arial, Helvetica, sans-serif;
    }
</style>
<template>
    <div class="todo-item">
        <p>
            {{ todo.title }}
        </p>
    </div>
</template>

<script>
   export default {
       name: "TodoItem",
       props: ["todo"]
   }
</script>

<style scoped>
    .todo-item {
        padding: 10px;
        border-bottom: 1px #ccc dotted;
    }

    .is-complete {
        text-decoration: line-through;
    }

    .del {
        background: #ff0000;
        color: #fff;
        border: none;
    }
</style>
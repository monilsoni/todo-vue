<template>
  <div id="app">
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
  import Todos from '../components/Todos'
  import AddTodo from "../components/AddTodo";
  import axios from "axios";

  export default {
    name: 'Home',
    components: {
      Todos,
      AddTodo
    },
    data() {
      return {
        todos: []
      }
    },
    methods: {
      deleteTodo(id) {
        axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
                .then(() => this.todos = this.todos.filter(todo => todo.id !== id))
                .catch(err => console.log(err));

      },
      addTodo(newTodo) {
        const {title, completed} = newTodo;
        axios.post('https://jsonplaceholder.typicode.com/todos', {
          title, completed
        })
                .then(res => this.todos.push(res.data))
                .catch(err => console.log(err))
      }
    },
    created() {
      axios.get('https://jsonplaceholder.typicode.com/todos?_limit=5')
              .then(res => this.todos = res.data)
              .catch(err => console.log(err));
    }
  }
</script>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    background-color: #e4f5ef;
  }

  .btn {
    display: inline-block;
    border: none;
    background: #2c3e50;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }

  .btn:hover {
    background: #4e6e8e;
  }
</style>


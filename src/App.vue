<template>
    <div id="app">
        <HelloWorld msg="Hello, Monil."/>
        <Todos v-bind:todos="todos"/>
    </div>
</template>

<script>
    import HelloWorld from "./components/HelloWorld";
    import Todos from './components/Todos'

    export default {
        name: 'App',
        components: {
            Todos,
            HelloWorld
        },
        data() {
            return {
                todos: [
                    {id: 1, title: "Todo 1", completed: false},
                    {id: 2, title: "Todo 2", completed: true},
                    {id: 3, title: "Todo 3", completed: true}
                ]
            }
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
        margin-top: 60px;
    }
</style>

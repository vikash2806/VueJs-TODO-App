<template>
  <div id="app">
    <Header></Header>
    <AddTodo v-on:add-Todo="addTodo"></AddTodo>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Header from './components/layout/Header'
import Todos from './components/Todos'
import AddTodo from './components/AddTodo'
export default {
  name: 'App',
  components: {
    Header,
    Todos,
    AddTodo,
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Todo One",
          completed: true,
        },
        {
          id: 2,
          title: "Todo Two",
          completed: true,
        },
        {
          id: 3,
          title: "Todo Three",
          completed: false,
        },
        {
          id: 4,
          title: "Todo Four",
          completed: false,
        },
        {
          id: 5,
          title: "Todo Five",
          completed: false,
        },
        {
          id: 6,
          title: "Todo six",
          completed: false,
        },
        {
          id: 7,
          title: "Todo seven",
          completed: false,
        },
      ]
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo)
    {
      this.todos = [...this.todos, newTodo];
    }
  }
}
</script>

<style>
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body{
  font-family:Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
.btn{
  display:inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}
.btn:hover {
  background: #666;
}
</style>

<template>
  <div id="app">
  <TodoHeader/>
  <TodoInput @sendTodo="parentSendTodo"/>
  <TodoList :todoList="todoList"/>
  </div>
</template>

<script>
import TodoHeader from './components/TodoHeader';
import TodoInput from './components/TodoInput';
import TodoList from './components/TodoList';



export default {
  name: 'App',
  components: {TodoHeader, TodoInput, TodoList},
  data() {
    return {
      id: 0,
      todoList: []
    }
  },
  methods:{
    parentSendTodo(todo) {
      var obj = {
        id: ++this.id,
        todo: todo
      }
      this.todoList.push(obj)
    }
  }
}
</script>

<style>

</style>

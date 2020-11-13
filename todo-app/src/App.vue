<template>
  <div id="app">
  <TodoHeader/>
  <TodoInput @sendTodo="parentSendTodo"/>
  <TodoList :todoList="todoList"
    @removeItem="parentDelTodo"
  /> 
  <TodoFooter @removeAll="parentDelAll"/>
  </div>
</template>

<script> 
import TodoHeader from './components/TodoHeader';
import TodoInput from './components/TodoInput';
import TodoList from './components/TodoList';
import TodoFooter from './components/TodoFooter';

export default {
  name: 'App',
  components: {TodoHeader, TodoInput, TodoList, TodoFooter},
  created(){
    this.selTodoList();
  },
  data() {
    return {
      id: 0,
      todoList: []
    }
  },
  methods:{
    selTodoList(){
      this.$http.get('/api/selTodoList').then((res) => {
      this.todoList = res.data
    })
    },
    parentSendTodo(todo) {
    
    },
    parentDelTodo(id) {
    
    },
    parentDelAll(){
     
    }
  }
}
</script>

<style>

</style>

<template>
  <ul :class="changeClass">
    <MyItem 
      v-for="todo in todos" 
      :key="todo.id" 
      :todo="todo" 
      :deleteTodo="deleteTodo"
      :checkTodo="checkTodo">
    </MyItem>
  </ul>
</template>

<script>
import MyItem from "./MyItem";

export default {
  name: "MyList",
  components: { MyItem },
  props:['todos','checkTodo','deleteTodo'],
  computed:{
    changeClass(){
      return this.todos.length==0?'todo-empty':'toto-main';
    }
  }
};
</script>

<style scoped>
/* main */
.todo-main {
  margin-left: 0px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0px;
}

.todo-empty {
  height: 40px;
  line-height: 40px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding-left: 5px;
  margin-top: 10px;
}
</style>
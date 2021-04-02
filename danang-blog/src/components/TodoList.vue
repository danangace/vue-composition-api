<template>
  <div id="todo-list">
    <ul>
      <li v-for="(data,index) in todos" :key="index">
        {{data}}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'TodoList',
  props: {
    todos: Array
  },
  setup (props) {
    console.log(props.todos)
    // props.todos.forEach(todo => console.log(todo))
    return {
      todos: props.todos
    }
  }
}
</script>

<style scoped>
p{
  margin-bottom: 0px;
}
</style>
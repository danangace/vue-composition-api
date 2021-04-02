<template>
  <div class="home">
    <h1>My Todo List</h1>
    <todo-list :todos="todos"></todo-list>
    <form>
      <input type="text" placeholder="Masukkan todo" name="todo-input" v-model="todo">
      <button @click.prevent="handleSubmitTodo">Tambah Todo</button>
    </form>
  </div>
</template>

<script>
import { ref } from 'vue'
import TodoList from '../components/TodoList.vue'

export default {
  name: 'Home',
  components: {
    TodoList
  },
  setup () {
    const todo = ref('')
    const todos = ref([])

    const handleSubmitTodo = () => {
      todos.value.push(todo.value)
      todo.value = ''
    }

    return {
      todo,
      todos,
      handleSubmitTodo
    }
  }
}
</script>

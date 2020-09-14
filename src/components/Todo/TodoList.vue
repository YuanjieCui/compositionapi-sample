<template>
  <div>
    <form @submit.prevent="handleSubmit">
      <input type="text" v-model="content" />
    </form>
    <div v-for="todo in todos"  v-bind:key="todo.id" >
      <TodoItem :todo="todo" :removeTodo="removeTodo"/>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs, provide } from 'vue'
import { TodoSymbol, useTodo } from './useTodo.ts'
import TodoItem from './TodoItem.vue'

export default defineComponent ({
  components: {
    TodoItem
  },
  setup(){

    const state = reactive({
      content: ''
    })


    const todo = useTodo()

    provide(TodoSymbol, todo);

    const { todos, addTodo, removeTodo } = todo;

    const handleSubmit = () => {
      addTodo(state.content)
      state.content = ''
    }


    return {
      ...toRefs(state),
      todos,
      removeTodo,
      handleSubmit
    }
  }
})
</script>

<style scoped></style>

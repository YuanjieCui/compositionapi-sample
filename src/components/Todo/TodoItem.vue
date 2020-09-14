<template>
    <div>
      {{ todo.id }}
      {{ todo.text }}
      <button @click="remove()">x</button>
    </div>
</template>

<script lang="ts">
import { defineComponent, inject } from 'vue'
import { TodoSymbol } from './useTodo.ts'

export default defineComponent ({
  props: {
    todo: {
      type: Object
    }
  },

  setup(props) {
    const { removeTodo } = inject(TodoSymbol)
    const remove = () => {
      removeTodo(props.todo.id);
    }

    return {
      remove,
    }
  }
})
</script>

<style scoped></style>

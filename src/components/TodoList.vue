<template>
  <div>
    <ul>
      <li>Todo 1</li>
      <TodoItem 
        v-bind:todo="todo"
        v-for="(todo, i) in todos"
        v-bind:key="todo"
        v-bind:index="i"
        v-on:remove-todo="removeTodo"
      />
    </ul>
  </div>
</template>

<script>
import TodoItem from '@/components/TodoItem.vue'

export default {
  props: ['todos'],
  components: {
    TodoItem
  },
  methods: {
    removeTodo(id) {
      console.log(id)
      this.$emit('remove-todo', id);
      this.title = '';
    }
  }
}
</script>

<style scoped>
  ul {
    list-style: none;
    margin: 0;
    padding: 0;
  }
</style>

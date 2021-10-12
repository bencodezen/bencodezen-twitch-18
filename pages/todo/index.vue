<script setup>
import { reactive } from 'vue'

const todoStore = reactive({
  taskList: [
    {
      id: 1,
      label: 'Ramen'
    }
  ],
  userTaskInput: ''
})

const addNewTask = () => {
  todoStore.taskList.push({
    id: todoStore.taskList.length + 1,
    label: todoStore.userTaskInput
  })
  todoStore.userTaskInput = ''
}
</script>

<template>
  <div>
    <h1>Todo App</h1>
    <input
      type="text"
      v-model="todoStore.userTaskInput"
      @keyup.enter="addNewTask"
    />
    <ul>
      <li v-for="task in todoStore.taskList" :key="task.id">
        {{ task.label }}
      </li>
    </ul>
  </div>
</template>

<style></style>

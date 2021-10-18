<template>
  <hr />
  <h3>{{ task.text }}</h3>
  <p>{{ task.day }}</p>
  <button @click="onTaskDelete(task.id)">Delete</button>
</template>

<script>
export default {
  name: 'Task',
  props: {
    task: Object
  },
  methods: {
    onTaskDelete(id){
      this.$emit('delete-task', id)
    }
  }
}
</script>

<template>
  <Header title="Task Maanger" />
  <Button text="Add Task" />
  <Tasks @delete-task="deleteTask" :tasks="tasks" />
</template>

<script>
import Header from "./components/Header";
import Button from "./components/Button";
import Tasks from "./components/Tasks";

export default {
  name: "App",
  components: {
    Header,
    Button,
    Tasks,
  },
  data() {
    return {
      tasks: [],
    };
  },
  methods: {
    deleteTask(id) {
      if (confirm("Are you sure?")) {
        this.tasks = this.tasks.filter((task) => task.id !== id);
      }
    },
  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: "Doctors Appointment",
        day: "March 1st at 3 PM",
        reminder: true,
      },
      {
        id: 2,
        text: "Grocery Shopping",
        day: "April 1st at 3 PM",
        reminder: true,
      },
    ];
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

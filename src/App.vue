<template>
  <div id="app">
    <AddTask :tasks="tasks" @AddText="Add($event)" />
    <ListTask :tasks="tasks"/>
  </div>
</template>

<script>
import ListTask from "./components/ListTask";
import AddTask from "./components/AddTask";
export default {
  name: "App",
  components: {
    ListTask,
    AddTask
  },
  data: function() {
    return {
      tasks: []
    };
  },
  methods: {
    Add: function(event) {
      this.tasks.push({
        text: event.title,
        cor: event.color
      })
      }
    }
}
</script>
<style>
</style>
<template>
  <div id="add">
    <div class="form">
      <input type="text" placeholder="Add a task" v-model="title"/>
      <button @click="add">ADD</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "AddTask",
  props: ["tasks"],
  data: function() {
    return {
      title: "",
      color: "background: white"
    };
  },
  methods: {
    add: function() {
      this.$emit("AddText", {
        title: this.title,
        color: this.color
      });
    }
  }
};
</script>

<style>
#add {
  width: 565px;
  height: 50px;
  border: 0.5px solid #fff;
  margin: 100px auto 0 auto;
}


.form input {
  margin: 8px 0 10px 10px;
  user-select: none;
  border: 0.5px solid blue;
  border-radius: 4px;
  width: 300px;
  height: 30px;
  font-size: 17px;
}


.form button {
  margin-left: 140px;
  border: none;
  border-radius: 2px;
  width: 100px;
  height: 30px;
  cursor: pointer;
  transition-duration: 1.2s;
}

.form button:hover {
  background-color: rgb(25, 0, 255);
  color: rgb(22, 17, 17);
}
</style>
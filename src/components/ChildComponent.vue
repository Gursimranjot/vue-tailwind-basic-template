<template>
  <div>
    <div
      style="margin: 20px; background-color: #efefef"
      v-for="todo in todos"
      :key="todo.id"
    >
      <img :src="todo.mes" alt="" />
      <h1>{{ todo.title }}</h1>
      <p class="hello">{{ todo.completed }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "ChildComponent",
  methods: {
    callMe() {
      alert("Call this function from parent");
    },
  },
  watch: {
    message: function () {
      this.callMe();
    },
  },
  props: {
    todos: Array,
  },
};
</script>

<style scoped>
</style>
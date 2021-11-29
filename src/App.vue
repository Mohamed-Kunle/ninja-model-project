<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <h1>{{ title }}</h1>
  <input type="text" ref="name" />
  <button @click="handlerClick">click me</button>
</template>

<script>
export default {
  data() {
    return {
      title: "My first  apps",
    };
  },
  methods: {
    handlerClick() {
      const input = this.$refs.name;
      input.className = "Active";
    },
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

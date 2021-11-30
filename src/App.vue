<template>
  <h1>{{ title }}</h1>

  <!-- <input type="text" ref="name" />
  <button @click="handlerClick">click me</button> -->
  <p>Welcome...</p>
  <teleport to=".models" v-if="showModel">
    <Model theme="" @close="toggleModel">
      <!-- Default slot -->
      <h1>Sign up for the Giveaway</h1>
      <h4>Grap your ninja swag for half price</h4>

      <!-- Named slot -->
      <template v-slot:links>
        <a href="#">GET NOW!</a>
        <a href="#">MORE NOW!</a>
      </template>
    </Model>
  </teleport>

  <!-- Another model -->
  <teleport to=".models" v-if="showModelTwo">
    <Model @close="toggleModelTwo">
      <h1>Tesing</h1>
    </Model>
  </teleport>

  <button @click="toggleModel">Show model</button>
  <button @click="toggleModelTwo">Show model two</button>
</template>

<script>
import Model from './components/Model.vue';
export default {
  components: {
    Model,
  },
  data() {
    return {
      title: 'MY FIRST VUE APP',
      header: 'Sign up for the Giveaway',
      text: 'Grap your ninja swag for half  price',
      showModel: false,
      showModelTwo: false,
    };
  },
  methods: {
    // handlerClick() {
    //   const input = this.$refs.name;
    //   input.className = "Active";
    // },
    toggleModel() {
      this.showModel = !this.showModel;
    },
    toggleModelTwo() {
      this.showModelTwo = !this.showModelTwo;
    },
  },
};
</script>

<style>
#app,
.models {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
  font-size: 40px;
}
button {
  padding: 12px 18px;
  margin-left: 20px;
  background-color: rgb(169, 238, 169);
  color: black;
  border-radius: 0.25rem;
}
</style>

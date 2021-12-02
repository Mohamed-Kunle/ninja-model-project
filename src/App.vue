<template>
  <h1>{{ title }}</h1>

  <!-- <input type="text" ref="name" />
  <button @click="handlerClick">click me</button> -->
  <p>Welcome...</p>
  <div v-if="showModal">
    <Modal theme="" @close="toggleModal">
      <!-- Default slot -->
      <h1>Sign up for the Giveaway</h1>
      <h4>Grap your ninja swag for half price</h4>

      <!-- Named slot -->
      <template v-slot:links>
        <a href="#">GET NOW!</a>
        <a href="#">MORE NOW!</a>
      </template>
    </Modal>
  </div>

  <!-- Another model -->
  <div v-if="showModelTwo">
    <Modal @close="toggleModalTwo">
      <h1>Tesing</h1>
    </Modal>
  </div>

  <button @click="toggleModal">Show Modal</button>
  <button @click="toggleModalTwo">Show Modal two</button>
</template>

<script>
import Modal from './components/Modal.vue';

export default {
  components: {
    Modal,
  },
  data() {
    return {
      title: 'MY FIRST VUE APP',
      header: 'Sign up for the Giveaway',
      text: 'Grap your ninja swag for half  price',
      showModal: false,
      showModalTwo: false,
    };
  },
  methods: {
    // handlerClick() {
    //   const input = this.$refs.name;
    //   input.className = "Active";
    // },
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;

      console.log(this.showModalTwo);
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

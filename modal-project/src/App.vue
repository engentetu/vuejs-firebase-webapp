<template>
  <h1>{{ title }}</h1>
  <input type="text" ref="boo" />
  <button @click="handleClick">click me</button>

<div v-if="showModal">
  <Modal :header="header" :text="text" theme="sale" @close="toggleModal"/>
</div>
<button @click.shift="toggleModal">open Modal</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      title: "My First Vue App :)",
      header: "Sign up for the Giveway!!!",
      text: "something important!!",
      showModal: false
    };
  },
  methods: {
    handleClick() {
      console.log(this.$refs.boo);
      this.$refs.boo.classList.add("active");
      this.$refs.boo.focus();
    },
    toggleModal(){
      this.showModal = !this.showModal;
    }
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
  /* display: inline-block; */
  /* background-color: aquamarine; */
  padding-bottom: 10px;
  /* display: flex; */
  /* justify-content: center; */
}
</style>

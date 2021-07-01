<template>
  <h1>{{ title }}</h1>
  <p>Welcome to MichaelsCorner</p>
  <teleport to=".modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign up here</a>
        <a href="#">more info</a>
      </template>
      <h1>Giveaways for all!</h1>
      <p>Promos, Codes, discounts, news. Anything the heart desires!</p>
    </Modal>
  </teleport>

  <teleport to=".modals" v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <h1>Sign up to Newsletter</h1>
      <p>Grab a chair and join the corner talk!</p>
    </Modal>
  </teleport>

  <button @click="toggleModal"> Giveaways </button>
  <button @click="toggleModalTwo"> Newsletter </button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My First Vue App :)",
      showModal: false,
      showModalTwo: false,
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    }
  }
};
</script>

<style>
#app, .modals {
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
}
button {
  background: #bbb;
  padding: 10px;
  border: none;
  border-radius: 4px;
  margin: 10px;
  font-size: 16px;
  color: #333;
}
</style>

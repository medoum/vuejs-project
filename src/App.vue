<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <teleport to =".modals" v-if="showModal">
    <Modal theme="" @close="toggleModal">
      <template v-slot:links>
          <a href="#">sign up now</a>
          <a href="#">more info</a>
      </template>
      <h1>Mohamed Doumbouya</h1>
      <p>The daily app</p>
    </Modal>
  </teleport>

  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <h1>Sign up to the newsletter</h1>
      <p>For updates and promo codes!</p>
    </Modal>
  </div>
  <button @click.alt="toggleModal">Open Modal (alt)</button>
  <button @click.alt="toggleModalTwo">Open Modal</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data(){
    return{
      title : 'DAILY vue App :)',
      showModal: false,
      showModalTwo: false
    }
  },
  methods: {
    toggleModal(){
      this.showModal = !this.showModal;
    },
    toggleModalTwo(){
      this.showModalTwo = !this.showModalTwo;
    }
  }
}
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
h1{
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}

</style>

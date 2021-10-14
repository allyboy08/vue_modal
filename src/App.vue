<template>
  <h1>{{title}}</h1>
  <p>enter</p>
  <teleport to=".modals" v-if="showModal">
    <Modal theme="village" @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign</a>
        <a href="#">more</a>
      </template>
      <h1>giveaway</h1>
      <p>grab your ninja headband for a coin</p>
    </Modal>
  </teleport>

  <teleport to=".modals" v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <h1>newsletter</h1>
      <p>updates</p>
    </Modal>
  </teleport>
  <button @click.alt="toggleModal">open modal (alt)</button>
  <button @click="toggleModalTwo">open modal</button>
</template>

<script>
import Modal from './components/Modal'


export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'my first vue app',
      showModal: false,
      showModalTwo: false
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
    }
  }
}
</script>

<style>
#app .modals {
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
</style>

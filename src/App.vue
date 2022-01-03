<template lang="pug">
div.container.center-align
  h5 {{title}}
  p Welcome
  teleport(to=".modals" v-if="showModal")
    Modal(theme="" @close="toggleModal")
      template(v-slot:links)
        a(href="#") Sign Up
        a(href="#") More Info
      h1 Lorem Ipsum 
      p More lorem ipsum
  teleport(to=".modals" v-if="showModalTwo")
    Modal(@close="toggleModalTwo")
      h1 newsletter 
      p get updates
    
  button.small(@click="toggleModal") open modal (alt)
  button.small(@click="toggleModalTwo") open modal
</template>

<script>
import Modal from "./components/Modal.vue";
export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'Example using TELEPORT',
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
  },
}
</script>

<style>

</style>

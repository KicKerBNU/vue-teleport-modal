<template lang="pug">
div.container.center-align
  h5 {{title}}
  p Welcome
  teleport(to=".modals" v-if="showModal")
    Modal(theme="" @close="toggleModal")
      template(v-slot:links)
        button.small
          a(href="#") Sign Up
        button.small 
          a(href="#") More Info
      h5 Lorem Ipsum 
      p More lorem ipsum
  teleport(to=".modals" v-if="showModalTwo")
    Modal(@close="toggleModalTwo")
      h5 newsletter 
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

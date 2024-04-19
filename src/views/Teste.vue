<template>
    <Modal v-model:showModal="showModal" :modalTitle="'Meu  Texto'" @closeModal="modalClosed">
       
        <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Temporibus qui praesentium officia, culpa architecto nam doloremque, maiores impedit sint animi adipisci ipsum totam asperiores libero odio. Facere odit aliquam itaque!</p>
    </Modal>
    <div class="about">
      <h1>Teste</h1>
      <button @click="showModal = true">Mostar modal</button>
    </div>
  </template>
  <script>
  import Modal from '../components/myFirstComponente.vue'
  export default
   {
    
    data() {
        return {
            
            showModal: true
        }
    },

    

     components: {
        Modal,
     },
     methods: {
        modalClosed(){
            console.log('o modal está fechado!');
        }
     }
  } 

  
</script>
  <style>
  @media (min-width: 1024px) {
    .about {
      min-height: 100vh;
      display: flex;
      align-items: center;
    }
  }
  </style>
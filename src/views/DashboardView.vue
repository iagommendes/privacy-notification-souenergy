<template>
    <div>
      <h1>Dashboard</h1>
      <ModalComponent v-if="showModal" :showModal="showModal" @accept="handleAccept" />
    </div>
  </template>
  
  <script>
  import ModalComponent from '../components/ModalComponent.vue';
  
  export default {
    components: {
      ModalComponent
    },
    data() {
      return {
        showModal: false,
        currentUser: null
      };
    },
    created() {
      // Simular a recuperação do usuário logado
      fetch('http://localhost:3000/users/1') // Ajuste conforme necessário
        .then(response => response.json())
        .then(user => {
          this.currentUser = user;
          if (!user.acceptedPolicy) {
            this.showModal = true;
          }
        });
    },
    methods: {
      handleAccept() {
        this.showModal = false;
        this.currentUser.acceptedPolicy = true;
        fetch(`http://localhost:3000/users/${this.currentUser.id}`, {
          method: 'PATCH',
          headers: {
            'Content-Type': 'application/json'
          },
          body: JSON.stringify({ acceptedPolicy: true })
        });
      }
    }
  };
  </script>
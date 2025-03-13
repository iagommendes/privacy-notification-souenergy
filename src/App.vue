<template>
  <div id="app">
    <h1>Bem-vindo à Plataforma</h1>
    <button @click="login">Login</button>
    <ModalComponent v-if="showModal" :showModal="showModal" @accept="handleAccept" />
    <AdminView />
  </div>
</template>

<script>
import ModalComponent from './components/ModalComponent.vue';
import AdminView from './components/AdminView.vue';

export default {
  components: {
    ModalComponent,
    AdminView
  },
  data() {
    return {
      showModal: false,
      currentUser: null
    };
  },
  methods: {
    login() {
      // Simular login do usuário
      fetch('http://localhost:3000/users/1')
        .then(response => response.json())
        .then(user => {
          this.currentUser = user;
          if (!user.acceptedPolicy) {
            this.showModal = true;
          }
        });
    },
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
}
</script>
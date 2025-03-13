<template>
  <div class="dashboard">
    <img src="@/assets/logo.png" alt="Logo da Empresa" class="company-logo" />
    <h1 class="dashboard-title">Dashboard de Energia Solar</h1>
    <div class="card-container">
      <div class="dashboard-card">
        <h2 class="card-title">Monitoramento de Painéis</h2>
        <p class="card-content">Acompanhe o desempenho dos seus painéis solares em tempo real.</p>
      </div>
      <div class="dashboard-card">
        <h2 class="card-title">Relatórios de Economia</h2>
        <p class="card-content">Veja quanto você economizou com energia solar este mês.</p>
      </div>
      <div class="dashboard-card">
        <h2 class="card-title">Suporte Técnico</h2>
        <p class="card-content">Entre em contato com nosso suporte para resolver qualquer problema.</p>
      </div>
    </div>
    <button class="admin-button" @click="goToAdminPanel">Ir para o Painel Administrativo</button>
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
    const userId = localStorage.getItem('currentUserId');
    if (userId) {
      fetch(`http://localhost:3000/users/${userId}`)
        .then(response => response.json())
        .then(user => {
          this.currentUser = user;
          if (!user.acceptedPolicy) {
            this.showModal = true;
          }
        });
    }
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
    },
    goToAdminPanel() {
      this.$router.push('/admin');
    }
  }
};
</script>

<style scoped>
.dashboard {
  max-width: 1000px;
  margin: 40px auto;
  padding: 20px;
  /* glassmorphism effect */
  background-color: rgba(255, 255, 255, 0.5);
  backdrop-filter: blur(10px);
  border-radius: 12px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  text-align: center;
}

.company-logo {
  width: 100px;
  margin-bottom: 20px;
  border-radius: 8px;
}

.dashboard-title {
  color: var(--color-heading);
  font-size: 28px;
  margin-bottom: 30px;
}

.card-container {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  margin-bottom: 30px;
}

.dashboard-card {
  background-color: var(--color-background);
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  padding: 20px;
  margin: 10px;
  width: 30%;
  min-width: 200px;
}

.card-title {
  font-size: 20px;
  color: var(--color-heading);
  margin-bottom: 10px;
}

.card-content {
  font-size: 16px;
  color: var(--color-text);
}

.admin-button {
  background-color: var(--color-laranja);
  color: var(--color-background);
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.admin-button:hover {
  background-color: var(--color-amarelo-alaranjado);
}
</style>
<template>
  <div class="admin-panel">
    <img src="@/assets/logo.png" alt="Logo da Empresa" class="company-logo" />
    <h1 class="panel-title">Painel Administrativo</h1>
    <AdminView />
  </div>
</template>

<script>
import AdminView from '../components/AdminView.vue';

export default {
  components: {
    AdminView
  }
};
</script>

<style scoped>
.admin-panel {
  max-width: 1000px;
  margin: 40px auto;
  padding: 20px;
  background-color: var(--color-background-soft);
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

.panel-title {
  color: var(--color-heading);
  font-size: 28px;
  margin-bottom: 30px;
}
</style>
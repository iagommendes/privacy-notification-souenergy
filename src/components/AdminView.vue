<template>
  <div class="admin-card">
    <h2 class="admin-title">Usuários Cadastrados</h2>
    <div class="user-card-container">
      <div v-for="user in users" :key="user.id" class="user-card">
        <h3 class="user-name">{{ user.name }}</h3>
        <p>ID: {{ user.id }}</p>
        <p>Política Aceita: {{ user.acceptedPolicy ? 'Sim' : 'Não' }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      users: []
    };
  },
  created() {
    fetch('http://localhost:3000/users')
      .then(response => response.json())
      .then(data => {
        this.users = data;
      });
  }
};
</script>

<style scoped>
.admin-card {
  max-width: 800px;
  margin: 20px auto;
  padding: 20px;
  background-color: var(--color-background);
  border-radius: 12px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  text-align: center;
}

.admin-title {
  color: var(--color-heading);
  font-size: 24px;
  margin-bottom: 20px;
}

.user-card-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.user-card {
  background-color: var(--color-background-soft);
  border-radius: 8px;
  border: 1px solid var(--color-highlight);
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  padding: 15px;
  margin: 10px;
  width: 200px;
  text-align: left;
}

.user-name {
  font-size: 18px;
  color: var(--color-heading);
  margin-bottom: 10px;
}

p {
  font-size: 14px;
  color: var(--color-text);
  margin: 5px 0;
}
</style>
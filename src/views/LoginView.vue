<template>
  <div class="login-background">
    <div class="login">
      <h2>Login</h2>
      <form @submit.prevent="handleLogin">
        <input v-model="username" placeholder="Usuário" required />
        <input type="password" v-model="password" placeholder="Senha" required />
        <button type="submit">Entrar</button>
      </form>
      <p v-if="error">{{ error }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: '',
      password: '',
      error: ''
    };
  },
  methods: {
    handleLogin() {
      fetch(`http://localhost:3000/users?name=${this.username}&password=${this.password}`)
        .then(response => response.json())
        .then(users => {
          if (users.length > 0) {
            // Armazena o ID do usuário logado no localStorage
            localStorage.setItem('currentUserId', users[0].id);
            this.$router.push('/dashboard');
          } else {
            this.error = 'Usuário ou senha inválidos';
          }
        });
    }
  }
};
</script>

<style scoped>
.login-background {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background-position: center;
  background-size: cover;
  padding: 20px;

}

.login {
  background-color: var(--color-background);
  padding: 30px;
  border-radius: 12px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  text-align: center;
  width: 100%;
  max-width: 400px;
}

h2 {
  font-size: 24px;
  margin-bottom: 20px;
  color: var(--color-heading);
}

input {
  display: block;
  width: 100%;
  margin-bottom: 15px;
  padding: 12px;
  border: 1px solid #ccc;
  border-radius: 6px;
  font-size: 16px;
}

button {
  width: 100%;
  background-color: var(--color-highlight);
  color: var(--color-background);
  padding: 12px;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  font-size: 16px;
  transition: background-color 0.3s;
}

button:hover {
  background-color: var(--color-highlight-hover);
}

p {
  color: red;
  margin-top: 10px;
  font-size: 14px;
}
</style>
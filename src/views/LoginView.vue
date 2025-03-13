<template>
    <div class="login">
      <h2>Login</h2>
      <form @submit.prevent="handleLogin">
        <input v-model="username" placeholder="Username" required />
        <input type="password" v-model="password" placeholder="Password" required />
        <button type="submit">Entrar</button>
      </form>
      <p v-if="error">{{ error }}</p>
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
              this.$router.push('/dashboard');
            } else {
              this.error = 'Usuário ou senha inválidos';
            }
          });
      }
    }
  };
  </script>
  
  <style>
  .login {
    max-width: 300px;
    margin: 0 auto;
    text-align: center;
  }
  input {
    display: block;
    width: 100%;
    margin-bottom: 10px;
    padding: 8px;
  }
  </style>
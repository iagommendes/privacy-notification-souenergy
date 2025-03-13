<template>
    <div>
      <h2>Usuários que aceitaram a política</h2>
      <ul>
        <li v-for="user in acceptedUsers" :key="user.id">{{ user.name }}</li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        users: []
      };
    },
    computed: {
      acceptedUsers() {
        return this.users.filter(user => user.acceptedPolicy);
      }
    },
    created() {
      fetch('http://localhost:3000/users')
        .then(response => response.json())
        .then(data => {
          this.users = data;
        });
    }
  }
  </script>
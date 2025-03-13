<template>
    <div v-if="showModal" class="modal">
      <div class="modal-content">
        <p>Atualização da política de privacidade. Por favor, aceite para continuar.</p>
        <button @click="acceptPolicy">Aceitar</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: ['showModal'],
    methods: {
      acceptPolicy() {
        this.$emit('accept');
      }
    }
  }
  </script>
  
  <style>
  .modal {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .modal-content {
    background-color: white;
    padding: 20px;
    border-radius: 5px;
  }
  </style>
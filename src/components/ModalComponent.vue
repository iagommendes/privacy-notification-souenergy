<template>
  <div v-if="showModal" class="modal">
    <div class="modal-content">
      <p class="modal-text">Atualização da política de privacidade. Por favor, aceite para continuar.</p>
      <button @click="acceptPolicy" class="modal-button">Aceitar</button>
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

<style scoped>
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
  transition: opacity 0.3s ease;
}

.modal-content {
  background-color: var(--color-background);
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  text-align: center;
  max-width: 400px;
  width: 90%;
}

.modal-text {
  color: var(--color-text);
  margin-bottom: 20px;
}

.modal-button {
  background-color: var(--color-laranja);
  color: var(--color-background);
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.modal-button:hover {
  background-color: var(--color-amarelo-alaranjado);
}
</style>
<template>
  <div class="grandchild-container">
    <h3>GrandChild Component</h3>
    <button class="send-button" @click="sendData">Send Data to Parent</button>
  </div>
</template>

<script>
export default {
  methods: {
    sendData() {
      this.$emit('grandChildData', 'Data from GrandChild');
    }
  }
}
</script>

<style scoped>

.grandchild-container {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
  background-color: #f9f9f9;
  margin-bottom: 10px;
  text-align: center;
  background: transparent;
  backdrop-filter: blur(12px);
}

.send-button {
  padding: 10px 20px;
  border: none;
  background-color: #1bdd96;
  color: white;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
}

.send-button:hover {
  background-color: #0056b3;
}
</style>
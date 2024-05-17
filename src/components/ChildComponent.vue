<template>
  <div class="child-container">
    <h2>Child Component</h2>
    <grand-child-component @grandChildData="emitDataToParent"></grand-child-component>
    <div class="slot-content">
      <slot :data="dataToSend"></slot>
    </div>
  </div>
</template>

<script>
import GrandChildComponent from './GrandChildComponent.vue';

export default {
  components: {
    GrandChildComponent
  },
  data() {
    return {
      dataToSend: 'Data from Child'
    }
  },
  methods: {
    emitDataToParent(data) {
      this.$emit('childData', data);
    }
  }
}
</script>

<style scoped>
.child-container {
  padding: 15px;
  border: 1px solid #ccc;
  border-radius: 5px;
  background-color: #e9ecef;
  margin-bottom: 15px;
  background: transparent;
  backdrop-filter: blur(12px);
}

.slot-content {
  margin-top: 10px;
  padding: 10px;
  background-color: #f8f9fa;
  border: 1px solid #ddd;
  border-radius: 5px;
  background: transparent;
  backdrop-filter: blur(12px);
}
</style>
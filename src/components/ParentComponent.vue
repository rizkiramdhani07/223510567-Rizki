<template>
  <div class="parent-container">
    <h1>Parent Component</h1>
    <child-component @childData="handleChildData">
      <template v-slot:default="slotProps">
        <div class="child-data">
          <p>Data from Child: {{ slotProps.data }}</p>
          <p>Data received from GrandChild: {{ childData }}</p>
        </div>
      </template>
    </child-component>
  </div>
</template>

<script>
import ChildComponent from './ChildComponent.vue';

export default {
  components: {
    ChildComponent
  },
  data() {
    return {
      childData: ''
    }
  },
  methods: {
    handleChildData(data) {
      this.childData = data;
    }
  }
}
</script>

<style scoped>
.parent-container {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #bbb;
  border-radius: 5px;
  background-color: #f0f0f0;
  text-align: center;
  background: transparent;
  backdrop-filter: blur(12px);
}

.child-data {
  margin-top: 15px;
  padding: 10px;
  border: 1px solid #aaa;
  border-radius: 5px;
  background-color: #fff;
  background: transparent;
  backdrop-filter: blur(12px);
}
</style>
<template>
    <div class="child">
      <h2>Child Component</h2>
      <button @click="sendDataToParent">Send Data to Parent</button>
      <GrandchildComponent @grandchild-data="handleGrandchildData" />
      <slot></slot>
    </div>
  </template>
  
  <script>
  import GrandchildComponent from './GrandchildComponent.vue';
  
  export default {
    components: {
      GrandchildComponent,
    },
    methods: {
      sendDataToParent() {
        this.$emit('child-data', 'Data from Child Component');
      },
      handleGrandchildData(data) {
        this.$emit('child-data', data);
      },
    },
  };
  </script>
  
  <style scoped>
  .child {
    padding: 20px;
    border: 1px solid #ccc;
    margin: 20px;
    border-radius: 8px;
  }
  button {
    margin: 10px 0;
    padding: 10px;
    background-color: #42b983;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  button:hover {
    background-color: #2a8f6d;
  }
  </style>
  
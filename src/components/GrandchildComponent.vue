<template>
    <div class="grandchild">
      <h3>Grandchild Component</h3>
      <input v-model="inputData" placeholder="Enter some data" />
      <button @click="sendDataToChild">Send Data to Child</button>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        inputData: '',
      };
    },
    methods: {
      sendDataToChild() {
        this.$emit('grandchild-data', this.inputData);
      },
    },
  };
  </script>
  
  <style scoped>
  .grandchild {
    padding: 20px;
    border: 1px solid #ccc;
    margin: 20px;
    border-radius: 8px;
  }
  input {
    margin: 10px 0;
    padding: 10px;
    width: calc(100% - 22px);
    border-radius: 5px;
    border: 1px solid #ccc;
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
  
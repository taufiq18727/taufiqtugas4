<template>
    <div class="parent">
      <h1>Parent Component</h1>
      <p>Data from child: {{ childData }}</p>
      <ChildComponent @child-data="handleChildData">
        <template v-slot:default>
          <p>This is slot content from ParentComponent</p>
        </template>
      </ChildComponent>
    </div>
  </template>
  
  <script>
  import ChildComponent from './ChildComponent.vue';
  
  export default {
    components: {
      ChildComponent,
    },
    data() {
      return {
        childData: '',
      };
    },
    methods: {
      handleChildData(data) {
        this.childData = data;
      },
    },
  };
  </script>
  
  <style scoped>
  .parent {
    padding: 20px;
    border: 1px solid #ccc;
    margin: 20px;
    border-radius: 8px;
  }
  </style>
     
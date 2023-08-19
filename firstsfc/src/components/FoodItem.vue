<template> 
    <div v-on:click="countClicks">
      <h2>{{ name }}</h2>
      <p>{{ message }}</p>
      <p id="red">You have clicked me {{ count }} times.</p>
    </div>
  </template>
  
  <script>
    export default {
      data() {
        return {
          name: 'Apples',
          message: 'I like apples',
          count: 0
        }
      },
      methods: {
        countClicks() {
          this.count = this.count + 1;
        }
      }
    }
  </script>
  
  <style>
    #red {
      font-weight: bold ;
      color: rgb(144, 12, 12);
    }
  </style>
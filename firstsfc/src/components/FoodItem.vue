<template> 
    <div v-on:click="countClicks">
      <h2>{{ foodName }}</h2>
      <p>{{ foodDesc }}</p>
      <img src="../assets/apple.jpg" v-show="isFavorite">
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
      },
      props: {
        foodName: {
            type: String,
            required: true	
        },
        foodDesc: {
            type: String,
            required: false,
            default: 'This is the default description.'
        },
        isFavorite: {
            type: Boolean,
            required: false,
            default: false
        }
        }
    }
  </script>
  
  <style>
    #red {
      font-weight: bold ;
      color: rgb(144, 12, 12);
    }

    img {
        height: 1.5em;
        float: right;
    }
  </style>
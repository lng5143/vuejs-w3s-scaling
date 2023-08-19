<template>
  <h1>Food</h1>
  <div id="wrapper">
    <food-item 
      v-for="x in foods"
      key="x.name"
      v-bind:food-name="x.name"
      v-bind:food-desc="x.desc"
      v-bind:is-favorite="x.favorite"
      v-on:toggle-favorite="receiveEmit" />
    <!-- <food-item 
      food-name="Apples"
      food-desc="Apples are a type of fruit that grow on trees"
      v-bind:is-favorite="true" />
      <food-item 
      food-name="Pizza"
      food-desc="Pizza has a bread case with tomato sauce, cheese, and toppings on top."
      v-bind:is-favorite="false "/>
      <food-item 
      food-name="Rice"
      v-bind:is-favorite="false" /> -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: 'Hello World',
      foods: [
          { name: 'Apples',
            desc: 'Apples are a type of fruit that grow on trees.',
            favorite: true },
          { name: 'Pizza',
            desc: 'Pizza has a bread base with tomato sauce, cheese, and toppings on top.',
            favorite: false },
          { name: 'Rice',
            desc: 'Rice is a type of grain that people like to eat.',
            favorite: false },
          { name: 'Fish',
            desc: 'Fish is an animal that lives in water.',
            favorite: true },
          { name: 'Cake',
            desc: 'Cake is something sweet that tastes good.',
            favorite: false }
        ]
    }
  },
  methods: {
    receiveEmit(foodId) {
      const foundFood = this.foods.find(
        food => food.name === foodId
      );
      foundFood.favorite = !foundFood.favorite;
    }
  }
}
</script>

<style>
  #app > div:hover {
    cursor: pointer;
  }

  #wrapper {
    display: flex;
    flex-wrap: wrap;
  }

  #wrapper > div {
    border: dashed black 1px;
    margin: 10px;
    padding: 10px;
    background-color: lightgreen;
  }
</style>

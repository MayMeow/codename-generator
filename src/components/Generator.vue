<template>
  <div>
    <h1>Codename generator</h1>
    <div>
      <h2>{{generatedName}}</h2>
    </div>
    <button @click="generateName">Click me!</button>
    <div style="margin-top: 1em;">
      Total combinations: {{ totalCombination }}, Source code is available at <a href="https://github.com/MayMeow/codename-generator" target="_blank">GitHub</a>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'CodenameGenerator',
  data() {
    return {
      generatedName: 'You name goes here!',
      totalCombination: '',
      colors: [],
      animals: []
    }
  },
  props: {
  },

  mounted() {
    axios
        .get('/data.json')
        .then(response => (this.initializeArrays(response.data)));

    console.log('colors loaded');
  },

  methods: {
    generateName() {
      let selectedColor = this.colors[Math.floor(Math.random() * this.colors.length)];
      let selectedAnimal = this.animals[Math.floor(Math.random() * this.animals.length)];

      this.generatedName = selectedColor + ' ' + selectedAnimal;
    },

    initializeArrays(data) {
      this.colors = data.colors;
      this.animals = data.animals;

      this.totalCombination =  this.colors.length * this.animals.length;

      console.log(data);
    }
  }
}
</script>

<template>
  <Navbar />
  <div class="parent-container">
    <InputData :hovered="hovered" :setData="setData" :data="data"/>
    <OutputHeatmap :update-hovered="updateHovered" :data="data" />
  </div>
  <Footer />
  <img src="Ellipse5.svg" class="e-5" height="250px" />
  <img src="Ellipse4.svg" class="e-4" height="300px" />
</template>

<script>

import Navbar from './components/Nav-Bar.vue';
import InputData from './components/InputData.vue';
import OutputHeatmap from './components/OutputHeatmap.vue';
import Footer from './components/Footer-Component.vue';

export default {
  name: 'App',
  components: {
    Navbar,
    InputData,
    OutputHeatmap,
    Footer,
  },
  data() {
    return {
      data: [0,10,40,0,0,100,0,0,0],
      hovered: new Array(9).fill(0),
    }
  },
  methods: {
    setData(index, val) {
      this.data[index] = val;
      console.log(this.data);
    },
    updateHovered(index, action) {
      this.hovered[index] = action;
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  text-align: center;
  font-family: sans-serif;
}

.parent-container {
  display: flex;
  padding: 1rem;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  margin-bottom: 200px;
  padding-top: 160px;
}

.e-5 {
  position: absolute;
  right: 0;
  top: 0;
  z-index: -10;
  opacity: 0.2;
}

.e-4 {
  position: absolute;
  left: 0;
  top: 0;
  z-index: -10;
}

@media screen and (max-width:768px) {
  .parent-container {
    grid-template-columns: repeat(1, 1fr);
  }
}

input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

.secondary-text {
  color: rgb(152, 143, 143);
}
</style>

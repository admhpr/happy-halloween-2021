<template>
  <div class="controls">
    <input
      @input="onSliderInput"
      v-model="eyeAmount"
      type="range"
      min="1"
      max="100"
      class="slider"
    />
          
    <input type="color">
    <input type="color">
  </div>
  <div class="conatainer">
    <Eye v-for="eye in Number(eyeAmount)" :key="eye" />
  </div>
</template>

<script lang="ts" >
import Eye from "./Eye.vue";
export default {
  components: {
    Eye,
  },
  data() {
    return {
      eyeAmount: 1,
    };
  },
  methods: {
    onSliderInput(e) {
      console.log(this.eyeAmount);
    },
  },
};
</script>

<style>
.conatainer {
  background-color: black;
  min-height: 100vh;
  max-width: 100%;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
}
body {
  margin: 0;
  height: 100vh;
}
</style>
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
  </div>
  <div class="conatainer">
    <Eye v-for="eye in eyeAmount" :key="eye" />
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
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}
body {
  margin: 0;
  height: 100vh;
}
</style>
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
    <button @click="onLessClick">Less -</button>
    <button @click="onMoreClick">More +</button>

    <span>
      <input type="color" v-model="irisColor" name="iris" />
      <label for="iris"> Iris </label>
    </span>
    <span>
      <input type="color" v-model="pupilColor" name="pupil" />
      <label for="pupil"> Pupil </label>
    </span>
  </div>
  <div class="container">
    <Eye
      v-for="eye in Number(eyeAmount)"
      :key="eye"
      v-bind="{ irisColor, pupilColor }"
    />
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
      irisColor: "#FFFFFF",
      pupilColor: "#FFFFFF",
    };
  },
  methods: {
    onSliderInput(e) {},
    onMoreClick() {
      if (this.eyeAmount < 100) {
        this.eyeAmount += 1;
      }
    },
    onLessClick() {
      if (this.eyeAmount > 0) {
        this.eyeAmount -= 1;
      }
    },
  },
};
</script>

<style>
.container {
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
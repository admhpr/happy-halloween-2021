<template>
  <div class="conatainer">
    <Eye />
  </div>
</template>

<script lang="ts" >
import Eye from "./Eye.vue";
export default {
  components: {
    Eye,
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
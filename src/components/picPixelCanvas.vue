<template>
  <div class="margie">
    <picPixelRow
      v-for="n in zoomNumber * 2"
      class="marge"
      :key="n"
      :selectedImage="selectedImage"
      :passedImageData="passedImageData"
      :zoomNumber="zoomNumber"
    />
  </div>
</template>

<script>
import picPixelRow from "./picPixelRow.vue";
export default {
  name: "picPixelCanvas",

  components: {
    picPixelRow
  },
  props: ["selectedImage", "passedImageData", "zoomNumber"]
};
</script>

<style scoped>
.margie {
  margin-top: -24px;
}
</style>
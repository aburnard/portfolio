
<template>
  <div>
    <div class="columns is-gapless is-mobile rowgapless">
      <div v-for="n in zoomNumber" :key="n" class="column">
        <box class="is-fullwidth is-fullheight">
          <picPixelPixel :selectedImage="selectedImage" :passedImageData="passedImageData" />
        </box>
      </div>
    </div>
  </div>
</template>
<script>
import picPixelPixel from "./picPixelPixel";

export default {
  name: "picPixelRow",
  props: ["selectedImage", "passedImageData", "zoomNumber"],

  components: {
    picPixelPixel
  },

  data() {
    return {
      selected: 5
    };
  }
};
</script>


<style>
</style>

<template>
  <div>
    <box class="is-fullwidth is-fullheight">
      <figure class="image is-square">
        <img class="imagine" @click="imaginePixel" :src="passedImageData[thisPixelSelectedImage]" />
        <img class="is-hidden" :src="invisibleImage" />
      </figure>
    </box>
  </div>
</template>

<script>
export default {
  name: "picPixelPixel",
  props: ["selectedImage", "passedImageData"],
  data() {
    return {
      thisPixelSelectedImage: 8,
      invisibleImage: ""
    };
  },

  methods: {
    imaginePixel() {
      this.thisPixelSelectedImage = 9;
      this.thisPixelSelectedImage = this.selectedImage;
      this.invisibleImage = "";
    }
  }
};
</script>



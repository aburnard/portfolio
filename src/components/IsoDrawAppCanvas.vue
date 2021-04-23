<template>
  <div>
    <section>
      <div class="columns is-mobile">
        <div class="column is-mobile">
          <b-numberinput controls-position="compact" v-model="ratio" step="5" min="1" max="80"></b-numberinput>
        </div>
        <div class="column is-mobile">
          <b-switch v-model="grabber">Pin Canvas</b-switch>
        </div>
        <div class="column is-mobile">
          <b-switch v-model="gridline">Visible Grid</b-switch>
        </div>
        <div class="column is-mobile">
          <div>
            <v-swatches v-model="color" swatches="text-advanced"></v-swatches>
          </div>
        </div>
      </div>

      <IsoDrawGrid
        :radiusRatio="ratio"
        :grabber="grabber"
        :pickedColor="color"
        :gridline="gridline"
      ></IsoDrawGrid>
    </section>
  </div>
</template>

<script>
import VSwatches from "vue-swatches";
import IsoDrawGrid from "./IsoDrawGrid.vue";
import "vue-swatches/dist/vue-swatches.css";

export default {
  name: "IsoDrawApp",
  data() {
    return {
      ratio: 30,
      grabber: true,
      isActive: true,
      gridline: true,
      imageData: "",
      color: "#1CA085"
    };
  },

  components: {
    IsoDrawGrid,
    VSwatches
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>

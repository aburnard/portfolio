<template>
  <div id="IsoDrawGrid">
    <v-stage ref="stage" :draggable="grabber" :config="configKonva">
      <v-layer ref="layer">
        <v-regular-polygon
          @click="handleClick"
          @tap="handleClick"
          v-for="item in list"
          :key="item.id"
          :config="{
            x: item.x * recieveRadiusRatio.ratio,
            y: item.y * recieveRadiusRatio.ratio,

            id: item.id,

            sides: 3,
            radius: 100 * recieveRadiusRatio.ratio,
            fill: item.fill,
            stroke: visibleGrid,
            rotation: item.rotation,
          }"
        ></v-regular-polygon>
      </v-layer>
    </v-stage>
  </div>
</template>

<script>
const width = window.innerWidth * 3;
const height = window.innerHeight * 1.5;
export default {
  name: "IsoDrawGrid",
  props: ["radiusRatio", "grabber", "pickedColor", "gridline"],
  computed: {
    recieveRadiusRatio() {
      return { ratio: this.radiusRatio * 0.01 };
    },
    // visibleGrid() {
    //   return {"yellow"};
    // }
    visibleGrid: function() {
      if (this.gridline) {
        return "yellow";
      } else {
        return false;
      }
    }
  },
  data() {
    return {
      isActive: true,

      list: [],
      dragItemId: null,
      clickItemId: null,
      ratio: 0.3,

      configKonva: {
        width: width,
        height: height,
        strokeWidth: 4
      }
    };
  },

  methods: {
    handleClick(e) {
      const clickItemId = e.target.id();
      const item = this.list.find(i => i.id === clickItemId);
      item.fill = this.pickedColor;
      // if (item.fill == "blue") {
      //   item.fill = "red";
      // } else if (item.fill == "red") {
      //   item.fill = "yellow";
      // } else if (item.fill == "yellow") {
      //   item.fill = "blue";
      // }
    }
  },

  mounted() {
    for (let hexRow = 0; hexRow < 50; hexRow++) {
      for (let n = 0; n < 50; n++) {
        this.list.push({
          id: Math.round(Math.random() * 10000000).toString(),
          x: n * 170 + (hexRow % 2) * 85,
          fill: "blue",
          y: 150 * hexRow
        });
        this.list.push({
          id: Math.round(Math.random() * 10000000).toString(),
          rotation: 180,
          x: n * 170 + (hexRow % 2) * 85,
          fill: "blue",
          y: 150 * hexRow + 95
        });
      }
    }
  }
};
</script>

<style>
body {
  margin: 0;
  padding: 0;
}
</style>

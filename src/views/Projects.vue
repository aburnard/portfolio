<template>
  <div class="Home">
    <section>
      <b-tabs v-model="activeTab">
        <b-tab-item margin-right="-21px" padding="is-full-width" label="PicPixelApp">
          <picPixelApp />
        </b-tab-item>

        <b-tab-item label="IsoDraw">
          <IsoDrawApp />
        </b-tab-item>
      </b-tabs>
    </section>
  </div>
</template>

<script>
import picPixelApp from "../components/picPixelApp.vue";
import IsoDrawApp from "../components/IsoDrawApp.vue";
export default {
  components: {
    picPixelApp,
    IsoDrawApp
  },
  data() {
    return { activeTab: 0 };
  }
};
</script>

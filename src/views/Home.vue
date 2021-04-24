<template>
  <div>
    <section class="hero">
      <div class="content">
        <hr />
        <h1 is-primary>Welcome to pixeltown.org</h1>

        <p1>Featuring the web apps of Andrew Burnard</p1>
      </div>
      <div class="columns is-mobile is-centered">
        <div class="column is-one-third">
          <figure class="image">
            <img class="is-rounded" src="../assets/blbackdrop.png" />
          </figure>
        </div>
        <div class="column is-one-third">
          <b-carousel :indicator="false">
            <b-carousel-item v-for="(item, i) in 6" :key="i">
              <span class="image is-square">
                <img class="is-rounded" :src="getImgUrl(i)" />
              </span>
            </b-carousel-item>
          </b-carousel>
          <router-link to="/IsoDraw">IsoDraw</router-link>
        </div>

        <div class="column is-one-third">
          <b-carousel :indicator="false">
            <b-carousel-item v-for="(item, i) in 6" :key="i">
              <span class="image is-square">
                <img class="is-rounded" :src="getImgUrlTwo(i)" />
              </span>
            </b-carousel-item>
          </b-carousel>
          <router-link to="/PicPixelApp">PicPixelDraw</router-link>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
// @ is an alias to /src
//import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "home",
  components: {
    // HelloWorld
  },
  methods: {
    getImgUrl(value) {
      let thissource = require(`../../src/assets/isoslides/${value}.png`);
      return thissource;
    },
    getImgUrlTwo(value) {
      let thissource = require(`../../src/assets/picpixelslides/${value}.png`);
      return thissource;
    },
  },
};
</script>

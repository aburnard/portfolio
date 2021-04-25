<template>
  <div id="app">
    <div id="another navbar">
      <b-navbar class="has-background-light">
        <template slot="brand">
          <b-navbar-item>
            <router-link to="/">Pixeltown.org</router-link>
          </b-navbar-item>
          <b-navbar-item href="https://www.instagram.com/surfinlumberjack/">
            <b-icon icon="instagram"></b-icon>
          </b-navbar-item>
          <b-navbar-item href="https://github.com/aburnard">
            <b-icon icon="github"></b-icon>
          </b-navbar-item>
        </template>

        <template slot="end" class="is-primary">
          <b-navbar-item tag="div">
            <div class="buttons">
              <b-navbar-item>
                <router-link to="/PicPixelDraw">PicPixelDraw</router-link>
              </b-navbar-item>
              <b-navbar-item>
                <router-link to="/IsoDraw">IsoDraw</router-link>
              </b-navbar-item>
              <b-navbar-item>
                <router-link to="/About">About</router-link>
              </b-navbar-item>
            </div>
          </b-navbar-item>
        </template>
      </b-navbar>
    </div>

    <router-view />
  </div>
</template>


<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  font-weight: bold;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

.this_text_color {
  color: whitesmoke;
}

.other_text_color {
  color: rgb(245, 245, 245);
}
</style>

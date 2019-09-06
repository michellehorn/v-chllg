<template>
  <div id="app">
    <div class="header" :class="showNavbar">
      <h2>Header</h2>
    </div>
    <div id="nav">
      <router-link to="/">Cards</router-link>
      <router-link to="/coin">Coin challenge</router-link>
    </div>
    <div class="content">
      <router-view/>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      showNavbar: false
    };
  },
  methods: {
    handleScroll() {
      window.pageYOffset > 20
        ? (this.showNavbar = "false")
        : (this.showNavbar = "true");
    }
  },
  created() {
    window.addEventListener("scroll", this.handleScroll);
  },
  destroyed() {
    window.removeEventListener("scroll", this.handleScroll);
  }
};
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding-top: 80px;
  width: 200px;
  a {
    font-weight: bold;
    color: #2c3e50;
    padding: 1em 0.3em;
    display: block;
    text-align: left;
    &.router-link-exact-active {
      color: #42b983;
    }
  }
  position: fixed;
  left: 0;
  top: 0;
  bottom: 0;
}
.content {
  padding-top: 80px;
}
.header {
  box-shadow: 2px 2px 10px 10px gray;
  width: 100%;
  top: 0;
  left: 0;
  position: absolute;
  margin-bottom: 150px;
  height: 60px;
  padding: 10px 0px;
  &.false {
    opacity: 0;
    animation-duration: 1s;
    animation-name: opacityOff;
  }
  &.true {
    opacity: 1;
    animation-name: opacityOn;
    animation-duration: 1s;
  }
}
@media screen and (max-width:500px) {
  #nav {
    position: absolute;
    display: flex;
  }
  .content {
    padding-top: 100px;
  }
}
</style>

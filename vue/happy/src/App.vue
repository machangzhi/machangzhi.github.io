<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <div>
      <button @click="goAbout">go {{url}}</button>
    </div>
    <HelloWorld msg="Welcome to Your Vue.js + TypeScript App" />
    <router-view></router-view>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import HelloWorld from "./components/HelloWorld.vue";

@Component({
  components: {
    HelloWorld
  }
})
export default class App extends Vue {
  private url: String = "about";
  private goAbout(): void {
    if (this.url === "about") {
      this.$router.push(`/about`);
      this.url = "home";
    } else {
      this.$router.push(`/`);
      this.url = "about";
    }
  }
}
</script>

<style lang="less">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

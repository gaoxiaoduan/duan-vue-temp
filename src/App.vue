<template>
  <div id="app">
    <router-view></router-view>
    <div class="router">
      <router-link
        v-for="item in routesList"
        :to="{ path: item.path }"
        :key="item.path"
        >{{ item.name }}</router-link
      >
    </div>
    <img alt="Vue logo" src="./assets/img/logo.png" />
    <HelloWorld msg="a duan vue template" />
  </div>
</template>

<script>
import HelloWorld from "components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
  },
  data: function() {
    return {
      routesList: [],
    };
  },
  created: function() {},
  mounted: function() {
    this.routesList = [...this.$router.options.routes];
    console.log(this.routesList);
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.router > a {
  margin-right: 10px;
}
</style>

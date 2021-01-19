<template>
  <div id="app">
    <div class="row">
      <div class="menu">
        <button v-for="tab in tabs" :key="tab" @click="selected = tab;">
          {{ tab }}
        </button>
      </div>
      <Profile></Profile>
      <component :is="selected"></component>
    </div>
    <div class="circle1"></div>
    <div class="circle2"></div>
  </div>
</template>

<script>
  import Profile from "./components/Profile";
  import Projets from "./components/Projets";
  import Infos from "./components/Infos";

  export default {
    name: 'App',
    data: function() {
      return {
        tabs: ["Infos", "Projets"],
        selected: "Infos"
      };
    },
    components: {
      Profile,
      Projets,
      Infos
    }
  };
</script>

<style lang="scss" scoped>
  @import "./style/app";
</style>

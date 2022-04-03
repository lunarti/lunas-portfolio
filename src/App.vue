<template>
  <div id="app">
    <div class="nav">
      <NavBar />
    </div>
    <router-view/>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import NavBar from '@/components/NavBar.vue'; // @ is an alias to /src

export default defineComponent({
  name: 'HomeView',
  components: {
    NavBar,
  },
});
</script>

<style lang ="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

</style>

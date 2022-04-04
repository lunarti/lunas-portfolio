<template>
  <div id="app">
    <div class="nav">
      <NavBar/>
      
    </div>
    <router-view/>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import NavBar from '@/components/NavBar.vue'; // @ is an alias to /src


export default defineComponent({
  name: 'App',
  components: {
    NavBar,
  },
});
</script>

<style lang ="scss">

@import url(https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap);
#app {
 font-family: 'Press Start 2P', cursive;
  text-align: center;
    color: #2c3e50;
}

</style>

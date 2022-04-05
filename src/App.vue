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

#app {
 font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  text-align: center;
    color: #2c3e50;
}

</style>

<template>
  <header>
    <div class="bg-red-500 p-4 shadow-lg flex flex-col lg:flex-row">
        <router-link to="/" class="text-white px-4 py-2 m-1 rounded-md" 
        exact-active-class="bg-red-800"
        >Home</router-link>

        <router-link to="about" class="text-white px-4 py-2 m-1 rounded-md" 
        exact-active-class="bg-red-800"
        >About</router-link>
    </div>
  </header>
</template>

<style lang="scss" scoped>
</style>

<script>
export default {
  name: "NavBar",
};
</script>
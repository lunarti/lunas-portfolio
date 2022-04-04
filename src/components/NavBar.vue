<template>
  <header>
    <div class="bg-blue-500 p-4 shadow-base justify-center lg:flex-row md:flex-col sm:flex-col">
        <router-link to="/" class="text-white px-4 py-2 m-1 rounded-md" 
        exact-active-class="bg-blue-800"
        >Home</router-link>

        <router-link to="about" class="text-white px-4 py-2 m-1 rounded-md" 
        exact-active-class="bg-blue-800"
        >About</router-link>

         <router-link to="CVpdf" class="text-white px-4 py-2 m-1 rounded-md bg-black" 
        exact-active-class="text-black bg-blue-800"
        >CV</router-link>
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
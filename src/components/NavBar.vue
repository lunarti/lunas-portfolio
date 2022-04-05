<template>
  <header>
    <div class="bg-blue-500 p-4 shadow-base justify-center lg:flex-row md:flex-col sm:flex-col">
        <router-link to="/" class="text-white px-4 py-2 m-1 rounded-md border-b-4 border-sky-500" 
        exact-active-class="bg-blue-800"
        >Home</router-link>

         <router-link to="CVpdf" class="text-white px-4 py-2 m-1 rounded-md border-b-4 border-sky-500" 
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
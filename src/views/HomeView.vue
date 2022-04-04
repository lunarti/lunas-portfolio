<template>
  <div class="home">
    <h1 class="text-6xl m-4">
      <span class="text-blue-500">Victor Lunarti Valadão</span>
    </h1>
    <div class="flex items-center w-full">
      <h1 class="mx-auto mt-10 text-xl md:text-5xl">GitHub Repos</h1>
    </div>

    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4">
      <div v-for="repo in repos" :key="repo.repoName" class="m-3 card rounded-lg ">
        <repoCards
          :repoName="repo.repoName"
          :repoDescription="repo.repoDescription" 
          :repoStarCount="repo.repoStarCount"
          :repoUrl="repo.repoUrl"
        />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import axios from "axios";
import repoCards from "@/components/repoCards.vue"


interface Repo {
  repoName: string,
  repoUrl: string,
  repoStarCount: number,
  repoDescription: string,
}

export default defineComponent({
  components: { repoCards },
  name: 'HomeView',
  data() {
    return {
      repos: [] as Repo[]
    };
  },
  mounted(){
    axios.get('https://api.github.com/users/lunarti/repos?sort=updated').then(response => {
      console.log(response);
      response.data.slice(0,10).forEach((element: { name: string; description: string; stargazers_count: number; html_url: string; }) => {
        this.repos.push({
          repoName: element.name,
          repoDescription: element.description,
          repoStarCount: element.stargazers_count,
          repoUrl: element.html_url,
        })
        
      });
    }).catch(console.error)
      
    
    },
    
});
</script>

<style lang="scss" scoped>
.card{
  transition: 1s;
  background: linear-gradient(45deg, 
  var(--c1, #e9e6db), 
  var(--c2, #2b85da) 51%, 
  var(--c1, #e9e8e4)) 
  var(--x, 0)/ 200%;
  
}
.card:hover{ --x: 100%; }
</style>
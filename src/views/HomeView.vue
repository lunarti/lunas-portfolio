<template>
  <div class="home">
    <h1 class="text-6xl m-4">
      <span class="text-red-500">Victor Lunarti Valadão</span>
    </h1>
    
    <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/>
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
  name: 'HomeView',
  data() {
    return {
      repos: [] as Repo[]
    };
  },
  mounted(){
    axios.get('https://api.github.com/users/lunarti/repos?sort=updated').then(response => {
      response.data.slice(1,10).forEach((element: any) => {
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

<template>
  <div class="home">
    <div class="hero mt-10">
      <HeroCard/>
    </div>
    <div class="w-full flex justify-center">
      <p class="w-2/3 text-2xl text-justify mt-10">
      Bacharel em Engenharia Elétrica com pretensão em se especializar em Desenvolvimento de Software e Hardware.
      Tem como objetivo a confecção de projetos que desenvolvam as seguintes habilidades: Multithread e FreeRTOSes, NodeJS, Websockets.
      Apaixonado pela Cultura Maker, faz projetos de Impressão 3D e IoT com Tasmota, EspHome e Home Assistant.
      </p>
    </div>
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
import HeroCard from "@/components/HeroCard.vue"


interface Repo {
  repoName: string,
  repoUrl: string,
  repoStarCount: number,
  repoDescription: string,
}

export default defineComponent({
  components: { repoCards,HeroCard },
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
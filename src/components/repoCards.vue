<template>
  <t-card
    base-class="h-full rounded-lg shadow-lg cursor-pointer hover:shadow-xl overflow-hidden"
    body-class="h-full"
    v-on:click="openLink()"
  >
    <div class="repo m-2 shadow-lg hover:shadow-xl transition duration-500 cursor-pointer p-8 h-96">
    <div flex>
      <span class="text-lg md:text-sm md:w-auto font-bold uppercase">{{  repoName  }}<br /></span>
      <div class="inline ml-auto text-xs">
          <span>Stars:</span>
          <span class="mr-1 text-red-500">{{  repoStarCount  }}</span>
      </div>
    </div>
    <div class="desc wrap w-full">
      <p class="p-6 text-lg md:text-xs">{{  repoDescription  }}</p>
    </div>

    </div>
  </t-card>
</template>
<style lang ="scss" scoped></style>
<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'repoCards',
  props: {
      repoName: String,
      repoUrl: String,
      repoStarCount: Number,
      repoDescription: String,
  },
  methods:{
    openLink(): void{
      window.open(this.repoUrl, "_blank");
    }
  },
});
</script>
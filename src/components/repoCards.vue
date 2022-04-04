<template>
    <div class="repo">{{ repoName  }}</div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'repoCards',
  props: {
      repoName: String,
      repoUrl: String,
      reporStarCount: Number,
      reporDescription: String,
  },
});
</script>
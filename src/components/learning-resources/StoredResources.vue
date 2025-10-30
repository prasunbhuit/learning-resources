<script lang="ts" setup>
  import { inject } from "vue";
  import LearningResources from "./LearningResources.vue";

  const defaultResource = [{ id: "" }];

  const storedResources = inject("storedResources", defaultResource);
</script>

<template>
  <ul>
    <LearningResources
      v-for="resources in storedResources"
      :key="resources.id"
      :resources="resources"
    />
  </ul>
</template>

<style lang="css" scoped>
  ul {
    list-style: none;
    margin: 0;
    padding: 0;
    margin: auto;
    max-width: 40rem;
  }
</style>

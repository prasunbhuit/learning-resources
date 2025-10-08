<script lang="ts" setup>
  import LearningResources from "./LearningResources.vue";
  const { storedResources } = defineProps(["storedResources"]);
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

<script setup lang="ts">
  import learningResources from "./components/learningResources.vue";
  const storedResources = [
    {
      id: "vuejs-official",
      title: "The Vue JS",
      description: "The official documentation of Vue JS",
      links: "https://vuejs.org",
    },
    {
      id: "search-engine",
      title: "Google",
      description: "Easy way the search the web",
      links: "https://google.com",
    },
  ];
</script>

<template>
  <ul>
    <learningResources :storedResources="storedResources" />
  </ul>
</template>

<style scoped></style>

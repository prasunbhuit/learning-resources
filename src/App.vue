<script setup lang="ts">
  import { ref } from "vue";
  import StoredResources from "./components/learning-resources/StoredResources.vue";
  import TheHeader from "./components/layouts/TheHeader.vue";

  const storedResources = ref([
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
    {
      id: "social-account",
      title: "Facebook",
      description: "Easy to connect with people",
      links: "https://facebook.com",
    },
  ]);
</script>

<template>
  <TheHeader title="Rember Me" />
  <StoredResources :storedResources="storedResources" />
</template>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap");

  * {
    box-sizing: border-box;
  }

  html {
    font-family: "Roboto", sans-serif;
  }

  body {
    margin: 0;
  }
</style>

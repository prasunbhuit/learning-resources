<script setup lang="ts">
  import BaseCard from "../UI/BaseCard.vue";
  import BaseButton from "../UI/BaseButton.vue";

  const { resources } = defineProps(["resources"]);
</script>

<template>
  <li>
    <base-card>
      <header>
        <h3>
          {{ resources.title }}
        </h3>
        <base-button mode="flat">Delete</base-button>
      </header>
      <p>{{ resources.description }}</p>
      <nav>
        <a :href="resources.links">View Resource</a>
      </nav>
    </base-card>
  </li>
</template>

<style scoped>
  li {
    margin: auto;
    max-width: 40rem;
  }

  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  h3 {
    font-size: 1.25rem;
    margin: 0.5rem 0;
  }

  p {
    margin: 0.5rem 0;
  }

  a {
    text-decoration: none;
    color: #ce5c00;
  }

  a:hover,
  a:active {
    color: #c89300;
  }
</style>

<style scoped></style>

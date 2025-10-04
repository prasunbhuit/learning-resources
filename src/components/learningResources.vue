<script setup lang="ts">
  const props = defineProps({ storedResources: { type: Array } });
</script>
<template>
  <div>
    <li
      v-for="list in props"
      :key="list.id"
    >
      {{ list.title }}
    </li>
  </div>
</template>

<style scoped></style>

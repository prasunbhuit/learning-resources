<script setup lang="ts">
  import resource from "../database/storedResources";
  import { ref, provide, computed } from "vue";
  import BaseCard from "../UI/BaseCard.vue";
  import BaseButton from "../UI/BaseButton.vue";
  import AddResources from "./AddResources.vue";
  import StoredResources from "./StoredResources.vue";

  const activeButton = ref(StoredResources);
  const setActiveButton = ref("stored-resources");

  const setStored = () => {
    activeButton.value = StoredResources;
    setActiveButton.value = "stored-resources";
  };

  const setStoredActive = computed(() => {
    return setActiveButton.value === "stored-resources" ? null : "flat";
  });

  const setAdd = () => {
    activeButton.value = AddResources;
    setActiveButton.value = "add-resources";
  };

  const setAddActive = computed(() => {
    return setActiveButton.value === "add-resources" ? null : "flat";
  });

  const storedResources = ref(resource);

  const addNewResources = (title: string, desc: string, link: string) => {
    const newResource = {
      id: new Date().toISOString(),
      title: title,
      description: desc,
      links: link,
    };

    storedResources.value.unshift(newResource);
    console.log(storedResources.value);

    activeButton.value = StoredResources;
    setActiveButton.value = "stored-resources";
  };

  provide("storedResources", storedResources);
  provide("addNewResources", addNewResources);
</script>

<template>
  <BaseCard>
    <BaseButton
      @click="setStored"
      :mode="setStoredActive"
      >Stored Resources</BaseButton
    >
    <BaseButton
      @click="setAdd"
      :mode="setAddActive"
      >Add New Resource</BaseButton
    >
  </BaseCard>
  <KeepAlive>
    <component :is="activeButton"></component>
  </KeepAlive>
</template>

<style scoped></style>

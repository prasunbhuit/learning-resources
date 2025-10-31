<script setup lang="ts">
  import { ref, inject } from "vue";
  import BaseCard from "../UI/BaseCard.vue";
  import BaseButton from "../UI/BaseButton.vue";

  const newTitle = ref("");
  const newDesc = ref("");
  const newLink = ref("");

  // const defaultNewResource = (title: string, desc: string, link: string) => {
  //   const newResource = {
  //     id: new Date().toISOString(),
  //     title: '',
  //     description: '',
  //     links: '',
  //   }

  type myAddNewResources = (x: string, y: string, z: string) => void;

  const addNewResources = inject<myAddNewResources>("addNewResources");

  const submitResources = () => {
    const enteredTitle = newTitle.value;
    const enteredDesc = newDesc.value;
    const enteredlink = newLink.value;
    console.log(addNewResources);
    if (addNewResources) {
      addNewResources(enteredTitle, enteredDesc, enteredlink);
    }
  };
</script>

<template>
  <BaseCard>
    <form @submit.prevent="submitResources()">
      <div class="form-control">
        <label for="title">Title</label>
        <input
          type="text"
          name="title"
          id="title"
          v-model="newTitle"
        />
      </div>
      <div class="form-control">
        <label for="description">Description</label>
        <textarea
          id="description"
          name="description"
          rows="2"
          v-model="newDesc"
        >
        </textarea>
      </div>
      <div class="form-control">
        <label for="link">Website</label>
        <input
          type="url"
          name="link"
          id="link"
          v-model="newLink"
        />
      </div>
      <BaseButton type="submit">Add Resources</BaseButton>
    </form>
  </BaseCard>
</template>

<style scoped>
  label {
    font-weight: bold;
    display: block;
    margin-bottom: 0.5rem;
  }

  input,
  textarea {
    display: block;
    width: 100%;
    font: inherit;
    padding: 0.15rem;
    border: 1px solid #ccc;
  }

  input:focus,
  textarea:focus {
    outline: none;
    border-color: #3a0061;
    background-color: #f7ebff;
  }

  .form-control {
    margin: 1rem 0;
  }
</style>

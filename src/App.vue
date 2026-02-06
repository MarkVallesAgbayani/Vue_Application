<script setup>
  import {ref} from 'vue';
  import sampleImage from './assets/images/sample_image.webp';

  const description = ref('This is a sample Vue component.');
  const url = ref('https://www.youtube.com/');
  const image = ref(sampleImage);

</script>

<template>
  <p>Description: {{ description }}</p>
  <a :href="url" target="_blank">Go to YouTube</a>

  <div>
    <p>This is image:</p>
    <img :src="image" alt="Sample Image" />
  </div>
</template>

<style scoped></style>

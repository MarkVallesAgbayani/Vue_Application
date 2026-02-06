<script setup>
  import ProductDetails from '@/components/ProductDetails.vue'
  import Darkmode from '@/components/Darkmode.vue'
  import About from '@/components/About.vue'



  const details = ["Props1" , "Props2", "Props3"];

</script>

<template>
  <About></About>

  <nav class="bg-gray-800 p-4 text-white text-center">
    <h1 class="text-2xl font-bold">My Vue App</h1>
  </nav>
  <ProductDetails :details="details"></ProductDetails>
  <hr>
  <Darkmode></Darkmode>
</template>

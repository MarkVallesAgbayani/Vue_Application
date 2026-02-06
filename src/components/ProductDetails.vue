<script setup>
import { ref, computed} from "vue";
import sampleImage from "@/assets/images/sample_image.webp";
import sampleImage2 from "@/assets/images/sampleimage2.webp";

const description = ref("This is a sample Vue component.");
const url = ref("https://www.youtube.com/");

const props = defineProps({
    details: {
        type: Array,
    }
});    

const propss = computed(() => {
    if (props.details){
        return "Its working";
    } else {
        return "Its not working";
    }
});

const stockStatus = ref(10);
const onSale = ref(true);
const inStockImg = ref(true);
const sizes = ref(["S", "M", "L", "XL"]);
const cart = ref(0);
const colors = ref([{ red: "Red" }, { green: "Green" }, { blue: "Blue" }]);

function addToCart() {
  cart.value++;
}

const objects = ref([
  {
    id: 1,
    name: "Object 1",
    size: "Small",
    image: sampleImage,
  },
  {
    id: 2,
    name: "Object 2",
    size: "Large",
    image: sampleImage2,
  },
]);
</script>

<template>
  <p class="text-center bg-gray-800 font-bold">
    Description: {{ description }}
  </p>
  <a :href="url" target="_blank" class="text-blue-500 underline"
    >Go to YouTube</a
  >

  <div>
    <p class="text-center">This is image:</p>
    <img :class="noStockImage" :src="!inStockImg" alt="" srcset="" />
  </div>

  <p v-if="stockStatus > 10">In stock</p>
  <p v-else-if="stockStatus <= 10 && stockStatus > 0">Low stock</p>
  <p v-else>Out of stock</p>

  <p v-if="onSale">On sale</p>
  <p v-else>Not on sale</p>

  <div>
    <ul class="list-none">
      <li v-for="size in sizes" :key="size">{{ size }}</li>
    </ul>
  </div>

  <div v-for="object in objects" :key="object.id">
    <p>
      {{ object.name }} - Size: {{ object.size }} <br />
      <img :src="object.image" alt="" srcset="" />
    </p>
  </div>

  <button @click="addToCart" type="button">Add to Cart</button>

  <div>Cart: {{ cart }}</div>

  <p :style="{ backgroundColor: colors.color }">Green</p>

  <p>{{ propss }}</p>
</template>

<style>
.noStockImage {
  background-image: url("./assets/images/outofstock.webp");
}
</style>

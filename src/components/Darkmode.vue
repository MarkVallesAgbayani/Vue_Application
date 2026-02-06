<script setup> 
import { ref, computed} from "vue";

const body = document.body;

function darkMode() {
    body.classList.toggle("darkMode");
};

</script>

<template>
    <div class="border-1">
        <p class="text-center bg-gray-800 font-bold">
            This is Dark Mode
        </p>
    </div>
    <button @click="darkMode" type="button">Click to Dark Mode</button>
</template>

<style>
.whiteMode {
    background-color: white;
}
.darkMode {
    background-color: black;
}
</style>
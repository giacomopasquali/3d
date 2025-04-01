<script setup>
import { TresCanvas } from "@tresjs/core";
import { GLTFModel, OrbitControls } from "@tresjs/cientos";
import { ref } from "vue";

defineProps({
  modelPath: String, // Path to the GLB file
});

const scale = ref(2); // Adjust as needed
</script>

<template>
  <TresCanvas clear-color="#202020">
    <TresPerspectiveCamera :position="[0, 1, 3]" />
    <OrbitControls />
    <!-- <AmbientLight :intensity="1.5" /> -->
    <GLTFModel :path="modelPath" :scale="scale" />
  </TresCanvas>
</template>

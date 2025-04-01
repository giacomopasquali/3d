<script setup>
import { ref } from 'vue'
import ModelViewer from './ModelViewer.vue'

const models = ref([
  '/models/lapnew.glb',
  '/models/lapnew.glb',
  '/models/lapnew.glb'
])

const currentIndex = ref(0)

const nextModel = () => {
  currentIndex.value = (currentIndex.value + 1) % models.value.length
}

const prevModel = () => {
  currentIndex.value = (currentIndex.value - 1 + models.value.length) % models.value.length
}
</script>

<template>
  <div class="carousel-container">
    <button @click="prevModel" class="nav-button">‹</button>
    <div class="model-view">
      <ModelViewer :modelPath="models[currentIndex]" />
    </div>
    <button @click="nextModel" class="nav-button">›</button>
  </div>
</template>

<style scoped>
.carousel-container {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 20px;
}

.model-view {
  width: 400px;
  height: 400px;
}

.nav-button {
  background: #444;
  color: white;
  border: none;
  font-size: 24px;
  padding: 10px 15px;
  cursor: pointer;
}
</style>

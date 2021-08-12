<script setup lang="ts">
import { ref, computed } from "vue"

const deg = ref(0)

const rotate = () => {
  deg.value = (deg.value + 20) % 360
}

const rotateDeg = computed(() => {
  return `rotateZ(${deg.value}deg)`
})
</script>

<template>
  <div class="container" @click="rotate">{{ rotateDeg }}</div>
</template>

<style scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  transform: v-bind("rotateDeg");
  padding: 4px;
  border: 2px solid gray;
  border-radius: 12px;
  height: 40px;
  width: 140px;
  cursor: pointer;
  user-select: none;
}

.container:hover {
  color: gray;
  transition: color, background-color 0.4s;
}
</style>

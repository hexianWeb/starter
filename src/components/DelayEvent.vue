<!-- eslint-disable no-console -->
<script setup lang="ts">
import { Html } from '@tresjs/cientos'
import { onBeforeMount } from 'vue'

function handleClick() {
  console.log('clicked delay event')
  alert('Delay event')
}
onBeforeMount(() => {
  console.log('before mount delay event')
})
</script>

<template>
  <TresMesh :position="[2, 2, 0]" name="Father" @click="handleClick">
    <TresSphereGeometry :args="[1, 1]" />
    <TresMeshNormalMaterial />
    <Html :position="[0, 0, 0]" center>
      <span class="cool-font">Click delay event</span>
    </Html>
  </TresMesh>
</template>

<style scoped>
.cool-font {
  pointer-events: none;
  font-family: 'Courier New', monospace;
  color: red;
  font-size: 24px;
  font-weight: bold;
}
</style>

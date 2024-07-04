<!-- eslint-disable no-console -->
<script setup lang="ts">
import { Html } from '@tresjs/cientos'
import { onBeforeMount } from 'vue'

function handleClick() {
  console.log('clicked Event event')
  alert('Normal event')
}

onBeforeMount(() => {
  console.log('before mount event')
})
</script>

<template>
  <TresMesh :position="[0, 2, 0]" name="Father" @click="handleClick">
    <TresSphereGeometry :args="[1, 1]" />
    <TresMeshNormalMaterial />
    <Html :position="[0, 0, 0]" center>
      <span class="cool-font">Click event</span>
    </Html>
  </TresMesh>
</template>

<style scoped>
.cool-font {
  pointer-events: none;
  font-family: 'Courier New', monospace;
  color: orange;
  font-size: 24px;
  font-weight: bold;
}
</style>

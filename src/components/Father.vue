<!-- eslint-disable no-console -->
<script setup lang="ts">
import { Html } from '@tresjs/cientos'
import {
  onBeforeMount,
  onBeforeUnmount,
  onMounted,
  onUnmounted,
} from 'vue'
import Child from './Child.vue'

onBeforeMount(() => {
  console.log('the Father onBeforeMount')
})

onMounted(() => {
  console.log('the Father onMounted')
})

onBeforeUnmount(() => {
  console.log('the Father onBeforeUnmount')
})

onUnmounted(() => {
  console.log('the Father onUnmounted')
})
</script>

<template>
  <TresGroup>
    <TresMesh :position="[2, 2, 0]" name="Father">
      <TresSphereGeometry :args="[1, 1]" />
      <TresMeshNormalMaterial />
      <Html :position="[0, 0, 0]" center>
        <span class="cool-font">I am Father</span>
      </Html>
    </TresMesh>
    <Child />
  </TresGroup>
</template>

<style scoped>
.cool-font {
  font-family: 'Courier New', monospace;
  color: green;
  font-size: 24px;
  font-weight: bold;
}
</style>

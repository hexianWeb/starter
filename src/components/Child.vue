<!-- eslint-disable no-console -->
<script lang="ts" setup>
import { Html } from '@tresjs/cientos'
import {
  onBeforeMount,
  onBeforeUnmount,
  onMounted,
  onUnmounted,
} from 'vue'

onBeforeMount(() => {
  console.log('the Child onBeforeMount')
})

onMounted(() => {
  console.log('the Child onMounted')
})

onBeforeUnmount(() => {
  console.log('the Child onBeforeUnmount')
})

onUnmounted(() => {
  console.log('the Child onUnmounted')
})
</script>

<template>
  <TresMesh
    :position="[0, 2, 0]"
  >
    <TresBoxGeometry :args="[1, 1, 1]" />
    <TresMeshNormalMaterial />
    <Html :position="[0, 0, 0]" center>
      <span class="cool-font">I am Child</span>
    </Html>
  </TresMesh>
</template>

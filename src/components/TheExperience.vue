<script setup lang="ts">
import { useLoop } from '@tresjs/core'
import { onMounted, ref, shallowRef } from 'vue'
import { OrbitControls } from '@tresjs/cientos'
import DelayEvent from './DelayEvent.vue'
import Event from './Event.vue'

const showRef = ref(false)

onMounted(() => {
  setTimeout(() => {
    showRef.value = !showRef.value
  }, 2000)
})
</script>

<template>
  <TresPerspectiveCamera :position="[5, 5, 5]" />
  <OrbitControls />
  <TresAmbientLight
    :intensity="0.5"
    color="red"
  />

  <TresDirectionalLight
    :position="[0, 2, 4]"
    :intensity="1"
    cast-shadow
  />
  <Event />
  <DelayEvent v-if="showRef" />
  <TresAxesHelper />
  <TresGridHelper :args="[10, 10, 0x444444, 'teal']" />
</template>

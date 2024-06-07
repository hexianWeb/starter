<script setup lang="ts">
import { OrbitControls } from "@tresjs/cientos";
</script>

<template>
  <TresGroup>
    <TresPerspectiveCamera :position="[5, 5, 5]" />
    <OrbitControls />
    <TresAmbientLight :intensity="0.5" color="red" />
    <TresMesh ref="boxRef" :position="[0, 2, 0]">
      <TresBoxGeometry :args="[1, 1, 1]" />
      <TresMeshNormalMaterial />
    </TresMesh>
    <TresDirectionalLight :position="[0, 2, 4]" :intensity="1" cast-shadow />
    <TresAxesHelper />
    <TresGridHelper :args="[10, 10, 0x444444, 'teal']" />
  </TresGroup>
</template>

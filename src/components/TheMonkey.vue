<script setup lang="ts">
import type { ThreeEvent } from '@tresjs/core'
import { useGLTF } from '@tresjs/cientos'
import '@tresjs/leches/styles'

function onClick(ev: ThreeEvent<MouseEvent>) {
  console.log('click', ev)

  ev.object.material.color.set('#008080')
}

function onDoubleClick(ev: ThreeEvent<MouseEvent>) {
  console.log('double-click', ev)

  ev.object.material.color.set('#FFD700')
}

function onPointerEnter(ev: ThreeEvent<MouseEvent>) {
  ev.object.material.color.set('#CCFF03')
}

function onPointerLeave(ev: ThreeEvent<MouseEvent>) {

  /*  ev.object.material.color.set('#efefef') */
}

function onPointerMove(ev: ThreeEvent<MouseEvent>) {

}

function onContextMenu(ev: ThreeEvent<MouseEvent>) {
  console.log('context-menu', ev)

  ev.object.material.color.set('#FF4500')
}

function onPointerMissed(ev: ThreeEvent<MouseEvent>) {
  console.log('pointer-missed', ev)
}
const { scene } = await useGLTF('/monkey.glb')
</script>

<template>
  <primitive
    :object="scene"
    @click="onClick"
    @double-click="onDoubleClick"
    @pointer-enter="onPointerEnter"
    @pointer-leave="onPointerLeave"
    @pointer-move="onPointerMove"
    @context-menu="onContextMenu"
    @pointer-missed="onPointerMissed"
  />
</template>

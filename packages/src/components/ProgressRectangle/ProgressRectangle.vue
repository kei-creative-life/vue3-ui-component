<script setup lang="ts">
defineProps({
  color: { type: String, default: '#000000' },
  width: { type: String, default: '24' },
  height: { type: String, default: '24' },
})
</script>

<template>
  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 32 32" :width="width" :height="height" :fill="color">
    <path d="M14 0 H18 V8 H14 z" transform="rotate(0 16 16)" opacity=".1">
      <animate attributeName="opacity" from="1" to=".1" begin="0" dur="1s" repeatCount="indefinite" />
    </path>
    <path d="M14 0 H18 V8 H14 z" transform="rotate(45 16 16)" opacity=".1">
      <animate attributeName="opacity" from="1" to=".1" begin="0.125s" dur="1s" repeatCount="indefinite" />
    </path>
    <path d="M14 0 H18 V8 H14 z" transform="rotate(90 16 16)" opacity=".1">
      <animate attributeName="opacity" from="1" to=".1" begin="0.25s" dur="1s" repeatCount="indefinite" />
    </path>
    <path d="M14 0 H18 V8 H14 z" transform="rotate(135 16 16)" opacity=".1">
      <animate attributeName="opacity" from="1" to=".1" begin="0.375s" dur="1s" repeatCount="indefinite" />
    </path>
    <path d="M14 0 H18 V8 H14 z" transform="rotate(180 16 16)" opacity=".1">
      <animate attributeName="opacity" from="1" to=".1" begin="0.5s" dur="1s" repeatCount="indefinite" />
    </path>
    <path d="M14 0 H18 V8 H14 z" transform="rotate(225 16 16)" opacity=".1">
      <animate attributeName="opacity" from="1" to=".1" begin="0.625s" dur="1s" repeatCount="indefinite" />
    </path>
    <path d="M14 0 H18 V8 H14 z" transform="rotate(270 16 16)" opacity=".1">
      <animate attributeName="opacity" from="1" to=".1" begin="0.75s" dur="1s" repeatCount="indefinite" />
    </path>
    <path d="M14 0 H18 V8 H14 z" transform="rotate(315 16 16)" opacity=".1">
      <animate attributeName="opacity" from="1" to=".1" begin="0.875s" dur="1s" repeatCount="indefinite" />
    </path>
  </svg>
</template>

<style scoped></style>

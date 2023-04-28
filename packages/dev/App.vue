<script setup lang="ts">
import VerticalTimeLine from '../src/components/VerticalTimeLine/VerticalTimeLine.vue'

const sections = [
  { title: 'タイトル1', content: 'ここに文章を入れます。ここに文章を入れます。ここに文章を入れます' },
  { title: 'タイトル2', content: 'ここに文章を入れます。ここに文章を入れます。ここに文章を入れます' },
]
</script>

<template>
  <ProgressRectangle width="48" height="48" color="black" />
  <ProgressCircular width="48" height="48" color="blue" />
  <VerticalTimeLine :sections="sections" />
  <WindowBox />
  <TerminalBox />
</template>

<style scoped></style>

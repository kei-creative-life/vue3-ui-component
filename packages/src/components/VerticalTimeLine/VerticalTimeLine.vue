<script setup lang="ts">
import { computed, defineProps } from 'vue'

type sectionType = { title: string; content: string }

type Props = {
  sections: sectionType[]
  titleColor: string
  balloonBgColor: string
  balloonBorderColor: string
  circleColor: string
}

const props = withDefaults(defineProps<Props>(), {
  titleColor: '#ffffff',
  balloonBgColor: '#c6cdd3',
  balloonBorderColor: '#ffffff',
  circleColor: '#2589d0',
  sections: () => [{ title: 'タイトル1', content: 'ここに文章を入れます。ここに文章を入れます。ここに文章を入れます' }],
})

const styles = computed(() => ({
  '--title-color': props.titleColor,
  '--baloon-bg-color': props.balloonBgColor,
  '--baloon-border-color': props.balloonBorderColor,
  '--circle-color': props.circleColor,
}))
</script>

<template>
  <div class="vertical-time-line" :styles="styles">
    <section v-for="(section, index) of sections" :key="index" class="vertical-time-line__section">
      <div class="vertical-time-line__label">
        {{ `Step ${index + 1}` }}
      </div>
      <p class="vertical-time-line__title">
        {{ section.title }}
      </p>
      <div class="vertical-time-line__content">
        <div class="vertical-time-line__img-wrap">
          <img
            class="vertical-time-line__img"
            src="https://cdn.vuetifyjs.com/images/parallax/material.jpg"
            alt=""
            width="320"
            height="180"
            loading="lazy"
            decoding="async"
          />
        </div>
        <p class="vertical-time-line__balloon">
          {{ section.content }}
        </p>
      </div>
    </section>
  </div>
</template>

<style scoped lang="css">
.vertical-time-line__section {
  position: relative;
  padding: 0.4em 1.5em 1.5em 2em;
}

.vertical-time-line__section:not(:last-child)::before,
.vertical-time-line__section::after {
  position: absolute;
  content: '';
}

.vertical-time-line__section:not(:last-child)::before {
  bottom: 0;
  left: 13px;
  transform: translateX(-50%);
  width: 3px;
  height: 100%;
  background-color: #d6dde3;
}

.vertical-time-line__section::after {
  top: 0;
  left: 0;
  width: 20px;
  height: 20px;
  border: 4px solid #fff;
  border-radius: 50%;
  background-color: #2589d0;
}

.vertical-time-line__label {
  margin-bottom: 0.5em;
  color: #bcbfc7;
  font-size: 1em;
}

.vertical-time-line__title {
  color: #333333;
  font-size: 1.2em;
  font-weight: 600;
  margin: 0 auto 0.5em;
}

.vertical-time-line__content {
  border-bottom: dashed 1px var(--baloon-bg-color);
  padding-bottom: 1.5em;
}

.vertical-time-line__img-wrap {
  max-width: 100%;
}

.vertical-time-line__img {
  width: 100%;
  height: auto;
}

.vertical-time-line__balloon {
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  padding: 0.7em;
  border: 3px solid #d6dde3;
  border-radius: 10px;
  font-size: 0.95em;
}

.vertical-time-line__balloon::before,
.vertical-time-line__balloon::after {
  position: absolute;
  top: -15px;
  width: 30px;
  height: 15px;
  clip-path: polygon(50% 0, 0 100%, 100% 100%);
  content: '';
}

.vertical-time-line__balloon::before {
  background-color: #d6dde3;
}

.vertical-time-line__balloon::after {
  top: -11px;
  background-color: #fff;
}

@media only screen and (min-width: 521px) {
  .vertical-time-line__content {
    display: flex;
    align-items: center;
    gap: 0 15px;
  }

  .vertical-time-line__img-wrap,
  .vertical-time-line__balloon {
    flex-basis: 50%;
  }

  .vertical-time-line__balloon::before,
  .vertical-time-line__balloon::after {
    top: unset;
    left: -15px;
    width: 15px;
    height: 30px;
    clip-path: polygon(0 50%, 100% 0, 100% 100%);
  }

  .vertical-time-line__balloon::after {
    top: unset;
    left: -11px;
  }
}
</style>

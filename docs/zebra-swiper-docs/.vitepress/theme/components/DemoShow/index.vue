<script lang="ts" setup>
import {
  EffectCube,
  EffectCreative,
  EffectCoverflow,
  EffectFlip,
  Autoplay
} from '@zebra-ui/swiper/modules'
import { reactive, ref } from 'vue'

const modules = ref([
  EffectCube,
  EffectCreative,
  Autoplay,
  EffectCoverflow,
  EffectFlip
])

const list = ref(
  Array.from({
    length: 5
  }).map((item, index) => {
    return {
      text: `Slide ${index + 1}`,
      id: index + 1
    }
  })
)

const creativeEffectOptions = reactive({
  prev: {
    shadow: true,
    origin: 'left center',
    translate: ['-5%', 0, -200],
    rotate: [0, 100, 0]
  },
  next: {
    origin: 'right center',
    translate: ['5%', 0, -200],
    rotate: [0, -100, 0]
  }
})

const creativeEffectOptions1 = reactive({
  prev: {
    shadow: true,
    translate: [0, 0, -400]
  },
  next: {
    translate: ['100%', 0, 0]
  }
})

const creativeEffectOptions2 = reactive({
  prev: {
    shadow: true,
    translate: [0, 0, -800],
    rotate: [180, 0, 0]
  },
  next: {
    shadow: true,
    translate: [0, 0, -800],
    rotate: [-180, 0, 0]
  }
})
</script>

<template>
  <div class="zebra-card-show">
    <div class="show-item">
      <z-swiper
        grabCursor
        loop
        autoplay
        :speed="1000"
        effect="cube"
        :modules="modules"
        :custom-style="{ height: '200px', width: '80%' }"
      >
        <z-swiper-item v-for="item in list" :key="item.id">
          <DemoItem
            class="demo-item"
            :text="item.text"
            height="100%"
          ></DemoItem>
        </z-swiper-item>
      </z-swiper>
    </div>
    <div class="show-item">
      <z-swiper
        grabCursor
        loop
        autoplay
        :speed="1000"
        effect="creative"
        :modules="modules"
        :creativeEffect="creativeEffectOptions"
        :custom-style="{ height: '200px', width: '80%' }"
      >
        <z-swiper-item v-for="item in list" :key="item.id">
          <DemoItem
            class="demo-item"
            :text="item.text"
            height="100%"
          ></DemoItem>
        </z-swiper-item>
      </z-swiper>
    </div>
    <div class="show-item">
      <z-swiper
        grabCursor
        loop
        autoplay
        :speed="1000"
        effect="creative"
        :modules="modules"
        :creativeEffect="creativeEffectOptions1"
        :custom-style="{ height: '200px', width: '80%' }"
      >
        <z-swiper-item v-for="item in list" :key="item.id">
          <DemoItem
            class="demo-item"
            :text="item.text"
            height="100%"
          ></DemoItem>
        </z-swiper-item>
      </z-swiper>
    </div>
    <div class="show-item">
      <z-swiper
        grabCursor
        loop
        autoplay
        :speed="1000"
        effect="creative"
        :modules="modules"
        :creativeEffect="creativeEffectOptions2"
        :custom-style="{ height: '200px', width: '80%' }"
      >
        <z-swiper-item v-for="item in list" :key="item.id">
          <DemoItem
            class="demo-item"
            :text="item.text"
            height="100%"
          ></DemoItem>
        </z-swiper-item>
      </z-swiper>
    </div>
    <div class="show-item">
      <z-swiper
        grabCursor
        loop
        autoplay
        :speed="1000"
        effect="coverflow"
        :modules="modules"
        :custom-style="{ height: '200px', width: '80%' }"
      >
        <z-swiper-item v-for="item in list" :key="item.id">
          <DemoItem
            class="demo-item"
            :text="item.text"
            height="100%"
          ></DemoItem>
        </z-swiper-item>
      </z-swiper>
    </div>
    <div class="show-item">
      <z-swiper
        grabCursor
        loop
        autoplay
        :speed="1000"
        effect="flip"
        :modules="modules"
        :custom-style="{ height: '200px', width: '80%' }"
      >
        <z-swiper-item v-for="item in list" :key="item.id">
          <DemoItem
            class="demo-item"
            :text="item.text"
            height="100%"
          ></DemoItem>
        </z-swiper-item>
      </z-swiper>
    </div>
  </div>
</template>

<style lang="scss">
@use '@zebra-ui/swiper/modules/effect-cube/effect-cube.scss';
@use '@zebra-ui/swiper/modules/effect-creative/effect-creative.scss';
@use '@zebra-ui/swiper/modules/effect-fade/effect-fade.scss';
@use '@zebra-ui/swiper/modules/effect-flip/effect-flip.scss';

.zebra-card-show {
  margin-top: 30px;
  padding: 30px;
  width: 100%;
  border-radius: 20px;
  box-shadow:
    0 0 var(--vp-c-neutral),
    0 0 var(--vp-c-neutral),
    0 36px 50px 20px var(--vp-c-gray-1);
  display: flex;
  flex-wrap: wrap;

  .show-item {
    width: 33%;
    height: 240px;
    box-sizing: border-box;
    padding: 20px;
    position: relative;
    min-width: 270px;

    .demo-item {
      border-radius: 10px;
    }
  }
}
</style>

<template>
  <div :style="{ marginLeft: '20px', marginRight: '20px' }">
    <swiper
      :options="swiperOptions"
      class="swiper"
      :modules="modules"
      :free-mode="true"
      :pagination="{
        clickable: true
      }"
      :slidesPerView="1"
      :spaceBetween="10"
      :breakpoints="{
        '640': {
          slidesPerView: 2,
          spaceBetween: 20
        },
        '768': {
          slidesPerView: 4,
          spaceBetween: 30
        },
        '1024': {
          slidesPerView: 5,
          spaceBetween: 40
        },
        '1280': {
          slidesPerView: 6,
          spaceBetween: 40
        }
      }"
    >
      <swiper-slide v-for="(image, index) in images" :key="index">
        <img :src="image" class="slider-image" />
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
import { Swiper, SwiperSlide } from 'swiper/vue'

export default {
  components: {
    Swiper,
    SwiperSlide
  },
  props: {
    images: Array
  }
}
</script>

<style lang="scss" scoped>
.slider-image {
  width: 100%;
  height: auto;
}

.swiper-slide:hover {
  transform: scale(1.05) !important;
  transition: transform 0.15s ease-in-out !important;
}
</style>

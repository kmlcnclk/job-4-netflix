<template>
  <div>
    <h2 :style="{ color: 'white', marginLeft: '20px' }">{{ text }}</h2>
    <Slider :images="smallImages" />
  </div>
</template>

<script>
import Slider from '../components/Slider.vue'

export default {
  components: {
    Slider
  },
  props: {
    text: String
  },
  data() {
    return {
      smallImages: [
        '/public/small-movie1.jpg',
        '/public/small-movie3.jpg',
        '/public/small-movie2.jpg',
        '/public/small-movie4.jpg',
        '/public/small-movie5.jpg',
        '/public/small-movie6.jpg',
        '/public/small-movie7.jpg',
        '/public/small-movie8.jpg'
      ]
    }
  }
}
</script>

<style></style>

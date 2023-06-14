<template>
  <div>
    <h2 :style="{ color: 'white', marginLeft: '20px' }">{{ text }}</h2>
    <Slider :images="smallImages" />
  </div>
</template>

<script>
import Slider from '../components/Slider.vue'
import SmallMovie1 from '../../public/small-movie1.jpg'
import SmallMovie2 from '../../public/small-movie2.jpg'
import SmallMovie3 from '../../public/small-movie3.jpg'
import SmallMovie4 from '../../public/small-movie4.jpg'
import SmallMovie5 from '../../public/small-movie5.jpg'
import SmallMovie6 from '../../public/small-movie6.jpg'
import SmallMovie7 from '../../public/small-movie7.jpg'
import SmallMovie8 from '../../public/small-movie8.jpg'

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
        SmallMovie1,
        SmallMovie2,
        SmallMovie3,
        SmallMovie4,
        SmallMovie5,
        SmallMovie6,
        SmallMovie7,
        SmallMovie8
      ]
    }
  }
}
</script>

<style></style>

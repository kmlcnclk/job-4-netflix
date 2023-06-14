<template>
  <header
    :style="{
      display: 'flex',
      justifyContent: 'space-between',
      backgroundColor: backgroundColor
    }"
  >
    <img src="/public/netflix-logo.png" class="netflix-logo" />
    <img src="/public/netflix-avatar.png" class="netflix-avatar" />
  </header>
  <main>
    <div :style="{ paddingBottom: '30px' }">
      <div class="banner">
        <div :style="{ margin: '20px', marginTop: '0px', paddingTop: '60px' }">
          <h1 class="title">Money Heist</h1>
          <div :style="{ display: 'flex' }">
            <button class="my-button" :style="{ marginRight: '20px' }">Play</button>
            <button class="my-button">My List</button>
          </div>
          <p class="movie-text">
            To carry out the biggest heist in history, a mysterious man called The Professor
            recruits a band of eight robbers who have a single characteristic: n...
          </p>
        </div>
        <div class="bottomBanner"></div>
      </div>

      <div>
        <h2 :style="{ color: 'white', marginTop: '-10px', marginLeft: '20px' }">
          NETFLIX ORIGINALS
        </h2>
        <Slider :images="largeImages" />
      </div>

      <CustomSlider v-for="text in sliderTexts" :text="text" :key="text" />
    </div>
  </main>
</template>

<script>
import Slider from '@/components/Slider.vue'
import CustomSlider from '@/components/CustomSlider.vue'

export default {
  name: 'Home',
  components: {
    Slider,
    CustomSlider
  },
  mounted() {
    window.addEventListener('scroll', this.updateBackgroundColor)
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.updateBackgroundColor)
  },
  methods: {
    updateBackgroundColor() {
      this.backgroundColor = window.scrollY >= 100 ? 'black' : 'transparent'
    }
  },
  data() {
    return {
      largeImages: [
        '/public/large-movie1.jpg',
        '/public/large-movie3.jpg',
        '/public/large-movie2.jpg',
        '/public/large-movie4.jpg',
        '/public/large-movie5.jpg',
        '/public/large-movie6.jpg',
        '/public/large-movie7.jpg',
        '/public/large-movie8.jpg'
      ],
      sliderTexts: [
        'Trending Now',
        'Top Rated',
        'Action Movies',
        'Comedy Movies',
        'Horror Movies',
        'Romance Movies',
        'Documentaries'
      ],
      backgroundColor: 'transparent'
    }
  }
}
</script>

<style lang="scss" scoped>
header {
  position: fixed;
  transition-property: all;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 0.5s;
  top: 0px;
  right: 0px;
  z-index: 20;
  left: 0px;
  height: 60px;
  .netflix-logo {
    margin: 20px;
    width: 80px;
    height: 20px;
  }
  .netflix-avatar {
    margin: 15px;
    margin-right: 20px;
    width: 30px;
    height: 30px;
  }
}
.banner {
  .movie-text {
    color: white;
    margin-top: 40px;
    width: 400px;
  }
  .title {
    color: white;
    font-size: 48px;
    margin-top: 0px;
    font-weight: 900;
  }

  .my-button {
    background-color: #333;
    color: white;
    border: none;
    padding: 10px 20px;
    opacity: 0.9;
    cursor: pointer;
    border-radius: 3px;
    transition: background-color 0.1s ease, color 0.1s ease;
    &:hover {
      background-color: white;
      color: #333;
      transition-delay: 0.1s;
    }
  }

  background-image: url('/banner.jpg');
  width: 100%;
  height: 500px;
  background-size: cover;

  .bottomBanner {
    width: 100%;
    height: 7.4rem;
    margin-top: 130px;
    background-image: linear-gradient(180deg, transparent, rgba(37, 37, 37, 0.61), #111);
  }

  @media (max-width: 768px) {
    .bottomBanner {
      margin-top: 110px;
    }
    .title {
      font-size: 36px;
    }
  }

  @media only screen and (max-width: 400px) {
    .movie-text {
      width: 320px;
    }
    .title {
      font-size: 32px;
    }
  }

  @media only screen and (max-width: 320px) {
    .movie-text {
      width: 290px;
    }
  }
}
</style>

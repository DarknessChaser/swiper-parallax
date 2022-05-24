<template>
  <swiper
    :style="{
      '--swiper-navigation-color': '#fff',
    }"
    :modules="modules"
    :speed="10000"
    :loop="true"
    :slides-per-view="1"
    :space-between="0"
    :freeMode="true"
    :parallax="true"
    :navigation="true"
    :keyboard="{
      enabled: true,
    }"
    :autoplay="{
      delay: 0,
      disableOnInteraction: false,
      pauseOnMouseEnter: true,
    }"
    :mousewheel="{ forceToAxis: true }"
    :scrollbar="{ draggable: true }"
  >
    <template #container-start>
      <div
        class="parallax-bg"
        data-swiper-parallax="-23%"
      >
        <div class="bg"></div>
        <div class="bg bg2"></div>
        <div class="bg bg3"></div>
      </div>
    </template>
    <swiper-slide>
      <div class="title" data-swiper-parallax="-300">Slide 1</div>
      <div class="subtitle" data-swiper-parallax="-300">Subtitle</div>
      <div class="text" data-swiper-parallax="-300">
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam
          dictum mattis velit, sit amet faucibus felis iaculis nec. Nulla
          laoreet justo vitae porttitor porttitor. Suspendisse in sem justo.
          Integer laoreet magna nec elit suscipit, ac laoreet nibh euismod.
          Aliquam hendrerit lorem at elit facilisis rutrum. Ut at ullamcorper
          velit. Nulla ligula nisi, imperdiet ut lacinia nec, tincidunt ut
          libero. Aenean feugiat non eros quis feugiat.
        </p>
      </div>
    </swiper-slide
    >
    <swiper-slide>
      <div class="title" data-swiper-parallax="-300">Slide 2</div>
      <div class="subtitle" data-swiper-parallax="-300">Subtitle</div>
      <div class="text" data-swiper-parallax="-300">
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam
          dictum mattis velit, sit amet faucibus felis iaculis nec. Nulla
          laoreet justo vitae porttitor porttitor. Suspendisse in sem justo.
          Integer laoreet magna nec elit suscipit, ac laoreet nibh euismod.
          Aliquam hendrerit lorem at elit facilisis rutrum. Ut at ullamcorper
          velit. Nulla ligula nisi, imperdiet ut lacinia nec, tincidunt ut
          libero. Aenean feugiat non eros quis feugiat.
        </p>
      </div>
    </swiper-slide
    >
    <swiper-slide>
      <div class="title" data-swiper-parallax="-300">Slide 3</div>
      <div class="subtitle" data-swiper-parallax="-300">Subtitle</div>
      <div class="text" data-swiper-parallax="-300">
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam
          dictum mattis velit, sit amet faucibus felis iaculis nec. Nulla
          laoreet justo vitae porttitor porttitor. Suspendisse in sem justo.
          Integer laoreet magna nec elit suscipit, ac laoreet nibh euismod.
          Aliquam hendrerit lorem at elit facilisis rutrum. Ut at ullamcorper
          velit. Nulla ligula nisi, imperdiet ut lacinia nec, tincidunt ut
          libero. Aenean feugiat non eros quis feugiat.
        </p>
      </div>
    </swiper-slide>
  </swiper>
</template>

<script lang="ts">
// import Swiper core and required modules
import {
  A11y, Autoplay, FreeMode, Keyboard, Mousewheel, Navigation, Parallax, Scrollbar,
} from 'swiper';
// Import Swiper styles
// eslint-disable-next-line import/extensions
import 'swiper/css';
// eslint-disable-next-line import/extensions
import 'swiper/css/a11y';
// eslint-disable-next-line import/extensions
import 'swiper/css/autoplay';
// eslint-disable-next-line import/extensions
import 'swiper/css/free-mode';
// eslint-disable-next-line import/extensions
import 'swiper/css/keyboard';
// eslint-disable-next-line import/extensions
import 'swiper/css/mousewheel';
// eslint-disable-next-line import/extensions
import 'swiper/css/navigation';
// eslint-disable-next-line import/extensions
import 'swiper/css/parallax';
// eslint-disable-next-line import/extensions
import 'swiper/css/scrollbar';
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue';
import { defineComponent } from 'vue';

export default defineComponent({
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules: [
        FreeMode, Autoplay, Mousewheel, Keyboard, Navigation, Scrollbar, A11y, Parallax,
      ],
    };
  },
});
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.swiper-free-mode > .swiper-wrapper { /*之前是ease-out*/
  transition-timing-function: linear;
}

.parallax-bg {
  position: absolute;
  left: 0;
  top: 0;
  width: 130%;
  height: 100%;
  background-size: cover;
  background-position: center;
}

.swiper-slide .title {
  font-size: 41px;
  font-weight: 300;
}

.swiper-slide .subtitle {
  font-size: 21px;
}

.swiper-slide .text {
  font-size: 14px;
  max-width: 400px;
  line-height: 1.3;
}

// 以下是花里胡哨的背景
.bg {
  animation:slide 3s ease-in-out infinite alternate;
  background-image: linear-gradient(-60deg, #6c3 50%, #09f 50%);
  bottom:0;
  left:-50%;
  opacity:.5;
  position:fixed;
  right:-50%;
  top:0;
  z-index:-1;
}

.bg2 {
  animation-direction:alternate-reverse;
  animation-duration:4s;
}

.bg3 {
  animation-duration:5s;
}

@keyframes slide {
  0% {
    transform:translateX(-25%);
  }
  100% {
    transform:translateX(25%);
  }
}
</style>

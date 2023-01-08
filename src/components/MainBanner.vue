<template>
  <div class="banner">
    <div class="slider">
      <img :src="srcImg">
      <button class="slider__left" @click="sliderBack"></button>
      <button class="slider__right" @click="sliderNext"></button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MainBanner',
  data: () => ({
    currentImg: 0,
    // indx: 0,
    interval: 3000,
    intervalId: null,
    sliderImg: [
      {
        src: 'https://tvoe.ru/upload/iblock/c62/vrb7vcgs611utyix5ci46n85deltqkel.jpg',
        link: ''
      },
      {
        src: 'https://tvoe.ru/upload/iblock/a45/1corwn9t3l1sjfxm4l3n3797fyyv9mqr.jpg',
        link: ''
      },
      {
        src: 'https://tvoe.ru/upload/iblock/f35/6r6254r9hzdo3s09rskmhpfyljcupv71.jpg',
        link: ''
      },
      {
        src: 'https://tvoe.ru/upload/iblock/4ce/zyuggun2ls6cyetgf1s11rxnb5r7r3c0.jpeg',
        link: ''
      },
      {
        src: 'https://tvoe.ru/upload/iblock/7be/03c0xnw478u8gq0smvfgsvab810pa3x0.jpg',
        link: ''
      },
      {
        src: 'https://tvoe.ru/upload/iblock/6f3/0s1jljg3cupoqyfu1j974rqz28ogj306.jpg',
        link: ''
      }
    ]
  }),
  mounted() {
    this.autoSlide()
  },
  methods: {
    autoSlide() {
      this.intervalId = setInterval(() => {
        this.sliderNext()
      }, this.interval)
    },
    sliderNext() {
      clearInterval(this.intervalId)
      this.autoSlide()
      if (this.currentImg + 1 === this.sliderImg.length) {
        this.currentImg = 0
        return
      }
      this.currentImg += 1
    },
    sliderBack() {
      clearInterval(this.intervalId)
      this.autoSlide()
      if (this.currentImg === 0) {
        this.currentImg = this.sliderImg.length - 1
        return
      }
      this.currentImg -= 1
    },
    // CHANGE() {
    //   this.currentImg = 1
    //   this.sliderImg.stop().animate({ left: '-100%' }, 500);
    //   this.sliderImg.eq(this.indx).stop().css({ left: '100%' }).animate({ left: 0 }, 500);
    // }
  },
  computed: {
    srcImg() {
      return this.sliderImg[this.currentImg].src
    }
  },
}
</script>

<style scoped>

.slider {
  position: relative;
}

img {
  width: 100%;
  /* position: absolute;
  left: 100%;
  top: 0 */
  /* animation: ani 3s ease 0.1s infinite reverse none; */
  /* animation: name duration timing-function delay iteration-count direction fill-mode; */
}

/* img:first-child {
  left: 0
} */

/* @keyframes ani {
  0% {
    transform: translateX(-150%);
    animation-play-state: paused;
  }
  50%{
    transform: none;
  }
  100% {
    animation-play-state: running;
  }
} */

button {
  background-repeat: no-repeat;
  background-position: center;
  width: 40px;
  height: 40px;
  background-color: #fff;
  border: none;
  border-radius: 3px;
  position: absolute;
  top: 50%;
  cursor: pointer;
}

button:hover {
  background-color: #383838;
  transition: all 0.5s ease;
}

.slider__left {
  background-image: url(https://img.icons8.com/ios-glyphs/30/000000/chevron-left.png);
  left: 10px;
}
.slider__left:hover {
  background-image: url(https://img.icons8.com/ios-glyphs/30/ffffff/chevron-left.png);
}

.slider__right {
  background-image: url(https://img.icons8.com/ios-glyphs/30/000000/chevron-right.png);
  right: 10px;
}

.slider__right:hover {
  background-image: url(https://img.icons8.com/ios-glyphs/30/ffffff/chevron-right.png);
}
</style>
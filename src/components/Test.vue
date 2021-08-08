<template>
  <div>
    <button class="han" @click="hanClick">
      <span class="han__style" :class="topLine"></span>
      <span class="han__style" :class="centerLine" v-show="centerShow"></span>
      <span class="han__style" :class="bottomLine"></span>
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      topStyle: false,
      centerStyle: false,
      bottomStyle: false,
      centerShow: true
    }
  },
  methods: {
    hanClick() {
      this.topStyle = !this.topStyle
      this.centerStyle = !this.centerStyle
      this.bottomStyle = !this.bottomStyle
      this.centerShow = !this.centerShow
    }
  },
  computed: {
    topLine() {
      return {
        top: this.topStyle
      }
    },
    centerLine() {
      return {
        center: this.centerStyle
      }
    },
    bottomLine() {
      return {
        bottom: this.bottomStyle
      }
    }
  }
}
</script>

<style scoped>
.han {
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
  width: 300px;
  height: 300px;
  background: #eee;
}

.han__style {
  margin: 30px 0;
  width: 200px;
  height: 8px;
  background: #000;
}

.top {
  animation-name: topAnimation;
  animation-fill-mode: forwards;
  animation-duration: 1s;
}

@keyframes topAnimation {
  100% {
    margin: 70px 0;
    transform-origin: left top;
    transform: rotate(45deg);
  }
}

.center {
  display: block;
  animation-name: centerAnimation;
  animation-fill-mode: forwards;
}

@keyframes centerAnimation {
  100% {
    display: none;
    background: red;
  }
}

.bottom {
  animation-name: bottomAnimation;
  animation-fill-mode: forwards;
  animation-duration: 1s;
}

@keyframes bottomAnimation {
  100% {
    margin: 70px 0;
    transform-origin: left top;
    transform: rotate(-45deg);
  }
}

</style>

<template>
  <div>
    <button class="han" @click="hanClick">
      <span class="han__style" :class="hanStyle"></span>
      <span class="han__style" :class="hanStyle"></span>
      <span class="han__style" :class="hanStyle"></span>
    </button>
    <div class="test"></div>
    <button class="button" @click="test" :class="classColorSet">
      <span class="button__style" :class="classStyle"></span>
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isHan: false,
      isActive: false,
      isShow: false
    }
  },
  methods: {
    test() {
      this.isActive = !this.isActive
      this.isShow = !this.isShow
    },
    hanClick() {
      this.isHan = !this.isHan
    }
  },
  computed: {
    classColorSet() {
      return {
        red: this.isActive,
        yellow: !this.isActive
      }
    },
    classStyle() {
      return {
        styletop: this.isShow
      }
    },
    hanStyle() {
      return {
        blue: this.isHan
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

.blue {
  background: blue;
  animation-name: hanAnimation;
  animation-duration: 1s;
}

@keyframes hanAnimation {
  100% {
    transform-origin: left top;
    transform: rotate(45deg);
  }
}

</style>

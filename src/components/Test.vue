<template>
  <div>
    <span class="test"></span>
    <button class="button" @click="test" :class="classColorSet">
      <span class="button__style" :class="classStyle"></span>
      
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isActive: false,
      isShow: false
    }
  },
  methods: {
    test() {
      this.isActive = !this.isActive
      this.isShow = !this.isShow
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
    }
  }
}
</script>

<style scoped>
.button {
  width: 300px;
  height: 300px;
  background: #eee;
}

.button__style {
  margin: 0 auto;
  display: block;
  width: 100px;
  height: 10px;
  background: #000;
}

.styletop {
  transform: rotate(45deg);
  transform-origin: top left;
}

.test {
  position: absolute;
  margin: 400px;
  display: block;
  width: 300px;
  height: 10px;
  background: red;
}

.test:hover {
  transform: rotate(45deg);
  transform-origin: top left;
  transition: 1s;
}
</style>

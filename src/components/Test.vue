<template>
  <div>
    <div id="dispArea" class="guideArea">
      <p id="guide">後からデザインを変更可能です</p>
      <input type="text" id="textBox" value="こんにちは">
    </div>

    <button @click="test">test</button>
    <button type="button" @click="cssTest()" :class="classColorSet">CSS変更</button>
  </div>
</template>

<script>

export default {
  el: '#dispArea',
  data() {
    return {
      isActive: true
    }
  },
  methods: {
    test() {
      this.isActive = !this.isActive
    },
    cssTest() {
      // javascriptでdiv領域にCSSを付与
      document.getElementById("dispArea").classList.add("addColor");
      // jQueryでテキストボックスにCSSを付与
      // $("#textBox").css( { 'font-size' : '18px' , 'color' : 'red' });
    }
  },
  computed: {
    classColorSet() {
      return {
        red: this.isActive,
        yellow: !this.isActive
      }
    }
  }
}
</script>

<style scoped>
/* 静的付与済み */
.guideArea {
  margin-bottom: 10px;
  padding: 5px;
  border: solid 2px;
  width: 300px;
}
/* 背景色を付与 */
.addColor {
  background-color: #d5ecce ;
}

.red {
  color: red;
}

.yellow {
  background: yellow;
}
</style>

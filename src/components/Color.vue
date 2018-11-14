<template>
  <div>
    <input type="range" min="0" max="255" step="1" :value="toRed(value)" ref="red" @input="update()" /><label>Red</label>
    <input type="range" min="0" max="255" step="1" :value="toGreen(value)" ref="green" @input="update()" /><label>Green</label>
    <input type="range" min="0" max="255" step="1" :value="toBlue(value)" ref="blue" @input="update()" /><label>Blue</label>
    <div class="preview" :style="backgroundStyle"></div>
  </div>
</template>

<script>
export default {
  name: 'Color',
  props: [ 'value' ],
  data: () => ({
    red: 0,
    green: 0,
    blue: 0
  }),
  computed: {
    backgroundStyle() {
      return `background-color: ${this.value}`;
    }
  },
  methods: {
    clear() {
      this.message = '';
    },
    hex(n) {
      n = (n - 0).toString(16);
      if (n.length < 2) {
        n = '0' + n;
      }
      return n;
    },
    update() {
      this.$emit('input', this.hexColor(this.$refs.red.value, this.$refs.green.value, this.$refs.blue.value));
    },
    hexColor(red, green, blue) {
      return '#' + this.hex(red) + this.hex(green) + this.hex(blue);
    },
    toRed(hexColor) {
      return parseInt(hexColor.substring(1, 3), 16);
    },
    toGreen(hexColor) {
      return parseInt(hexColor.substring(3, 5), 16);
    },
    toBlue(hexColor) {
      return parseInt(hexColor.substring(5, 7), 16);
    }
  }
}
</script>

<style>
.preview {
  width: 100px;
  height: 100px;
}
label {
  margin: 0 24px 0 12px;
}
</style>

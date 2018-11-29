<template>
  <div id="app">
    <h1>Vue <a href="https://vuejs.org/v2/guide/forms.html">two-way binding</a> demo</h1>
    <h2>Simple input element</h2>
    <input v-model="message" />
    <p>Message is: {{ message }}</p>
    <button @click="clear()">Clear</button>
    <h2>Custom color picker component</h2>
    <Color v-model="color" />
    <p>Color is: {{ color }}</p>
    <button @click="resetColor()">Reset Color</button>
    <h2><a href="https://github.com/boutell/vue-two-way-binding-demo">Source Code</a></h2>
  </div>
</template>

<script>
import Color from './components/Color.vue'
export default {
  name: 'app',
  data: () => ({
    message: 'initial message',
    color: '#ddeeff'
  }),
  methods: {
    clear() {
      this.message = '';
    },
    resetColor() {
      this.color = '#ddeeff'
    }
  },
  components: {
    Color
  }
}
</script>

<style>
</style>

<template>
  <div id="app">
    <h1>Two-way binding demo</h1>
    <h2>Simple input element</h2>
    <input v-model="message" />
    <p>Message is: {{ message }}</p>
    <button @click="clear()">Clear</button>
    <h2>Custom color picker component</h2>
    <Color v-model="color" />
    <p>Color is: {{ color }}</p>
    <button @click="resetColor()">Reset Color</button>
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

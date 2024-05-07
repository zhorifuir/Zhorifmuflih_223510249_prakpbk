<script setup>
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <div>
    <h1 :style="{ color: inputLength > 10 ? 'red' : '' }">{{ inputTitle }}</h1>
    <input type="text" v-model="inputValue" @input="updateTitle" />
    <p>{{ inputValue }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      inputValue: '',
      inputTitle: 'Input Title'
    }
  },
  computed: {
    inputLength() {
      return this.inputValue.length
    }
  },
  methods: {
    updateTitle() {
      this.inputTitle = this.inputValue
    }
  }
}
</script>

<style scoped>
h1 {
  font-size: 2rem;
  text-align: center;
}
input {
  width: 100%;
  padding: 0.5rem;
  font-size: 1rem;
}
p {
  font-size: 1.2rem;
  text-align: center;
}
</style>
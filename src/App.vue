<template>
  <section v-cloak>
    <h1>{{ name }}</h1>
    <input v-model="inputValue"/>
    <button @click="clearField">Clear this</button>
    <p v-if="inputValue">Some text: {{ inputValue }}</p>
    <p v-else>Some text will be here:</p>
  </section>


</template>

<script>
export default {
  data() {
    return {
      name: 'Hello world',
      inputValue: ''
    }
  },
  methods: {
    clearField() {
      this.inputValue = ''
    }
  }
}
</script>

<style>
[v-cloack] {
  display: none;
}
</style>

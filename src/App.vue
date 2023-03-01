<template>
  <section v-cloak>
    <h1>{{ name }}</h1>
    <input v-model="inputValue"/>
    <button @click="clearField">Clear this</button>
    <p v-if="inputValue">Some text will be here: {{ inputValue }}</p>
    <p v-else>Some text will be here:</p>

    <section>
      <button @click="showBox">Show box</button>
      <div class="box" v-if="ifVisible">toggle</div>
    </section>


  </section>


</template>

<script>
export default {
  data() {
    return {
      name: 'Hello world',
      inputValue: '',
      ifVisible: false
    }
  },
  methods: {
    clearField() {
      this.inputValue = ''
    },
    showBox() {
      this.ifVisible = !this.ifVisible
    }
  }
}
</script>

<style>
[v-cloack] {
  display: none;
}
.box{
  background-color: darkorange;
  width: 100px;
  text-align: center;
  margin-top: 10px;
}
</style>

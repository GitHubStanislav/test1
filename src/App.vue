<template>
  <section v-cloak>
    <h1>{{ name }}</h1>
    <input v-model="inputValue"/>
    <button @click="addPost">Add post</button>
    <button @click="clearField">Clear this</button>
    <p v-if="inputValue">Some text will be here: {{ inputValue }}</p>
    <p v-else>Some text will be here:</p>
    <div v-for="post in post" :key="post">
      <p class="post"> {{ post }} </p>
    </div>

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
      post: [],
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
    },
    addPost() {
      this.post.push(this.inputValue)
    }
  }
}
</script>

<style>
[v-cloack] {
  display: none;
}

.box {
  background-color: darkorange;
  width: 100px;
  text-align: center;
  margin-top: 10px;
}

.post {
  border: chartreuse 2px solid;
}
</style>

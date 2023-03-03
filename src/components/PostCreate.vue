<template>
  <section v-cloak>
    <h1>{{ logName }}</h1>
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

  name: "postCreate",
  data() {
    return {
      post: [],
      logName: 'Create post',
      inputValue: '',
      ifVisible: false,

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
      this.inputValue=''
      localStorage.setItem('posts',JSON.stringify(this.post))
    },

  }
}
</script>

<style scoped>
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
  border: #630152 2px solid;
  background-color: mintcream;
  width: 31%;
}
</style>
<template>
  <section v-cloak>
    <h1>{{ logName }}</h1>
    <input v-model="inputValue"/>
    <button @click="addPost">Add post</button>
    <button @click="clearField">Clear this</button>
    <p v-if="inputValue">Some text will be here: {{ inputValue }}</p>
    <p v-else>Some text will be here:</p>
    <div v-for="(post,index) in posts" :key="index">
      <p class="post"> {{ post }} </p>
    </div>
    <section>
      <button @click="showBox">Show box</button>
      <test-box :box-name="nameBox" v-if="ifVisible"/>
    </section>
  </section>
</template>

<script>
import TestBox from "@/components/TestBox.vue";
export default {
components:{TestBox},
  name: "postCreate",
  data() {
    return {
      posts: [],
      logName: 'Create post',
      inputValue: '',
      ifVisible: true,
      nameBox: 'Hello Box!'

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
      this.posts.push(this.inputValue)
      this.inputValue=''
      localStorage.setItem('posts',JSON.stringify(this.posts))
    },

  }
}
</script>

<style >
[v-cloack] {
  display: none;
}


.post {
  border: #630152 2px solid;
  background-color: mintcream;
  width: 31%;
}
</style>
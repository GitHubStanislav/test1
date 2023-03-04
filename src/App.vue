<template>

  <login-form/>
  <Post-create/>


</template>

<script>
import loginForm from "@/components/loginForm.vue";
import PostCreate from "@/components/PostCreate.vue";


export default {
  components: {
    PostCreate,
    loginForm,


  },
  data() {
    return {
      post: [],
      logList:[],
      name: 'Create post',
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

</style>

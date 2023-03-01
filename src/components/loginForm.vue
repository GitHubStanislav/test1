<template>
  <div class="formWrapper">
   <form @submit="handleSubmit">
     <h1>{{ title }}</h1>
     <input type="email" v-model="email">
     <input type="password" v-model="password">
     <button>Log in</button>
   </form>

  </div>
</template>

<script>
export default {
  name: "loginForm",
  data() {
    return {
      title: 'Login Form',
      email: '',
      password: '',
    }
  },
  methods:{
    handleSubmit(event){
      event.preventDefault()
      console.log(this.email , this.password)
    }
  }
}
</script>

<style scoped>
.formWrapper {
  display: flex;
  flex-direction: column;
}

.formWrapper input {
  width: 50%;
  margin-top: 5px;
}
button{
  display: block;
  margin-top: 10px;
}

</style>
<template>
  <div class="formWrapper">
    <form @submit="handleSubmit">
      <h1>{{ title }}</h1>
      <custom-input
          v-model="email"
          :model-value="email"
          :label="emailLabel"
          @custom-change="handleCustomChange"

      />

      <custom-input
          v-model="password"
          :model-value="password"
          :label="passwordLabel"
      />
      <p>{{uppercase}}</p>
      <button>Click</button>
    </form>
  </div>
</template>

<script>
import CustomInput from "@/components/CustomInput.vue";

export default {
  name: "loginForm",
  components: {CustomInput},
  data() {
    return {
      title: 'Login Form',
      email: '',
      password: '',
      emailLabel: 'Email',
      passwordLabel: 'Password',
      uppercase: ''
    }
  },
  methods: {
    handleSubmit(event) {
      event.preventDefault()
      console.log(this.email, this.password)
    },
    handleCustomChange (s) {
      this.uppercase = s
    }

  }
}
</script>

<style>
.formWrapper {
  display: flex;
  flex-direction: column;


}

.formWrapper input {
  width: 30%;
  margin-top: 5px;
  display: block;
}

button {
  margin-top: 10px;
  color: darkred;
}

</style>
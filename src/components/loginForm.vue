<template>
  <div class="formWrapper">
    <form @submit="handleSubmit">
      <h1>{{ title }}</h1>
      <custom-input
          v-for="(input,index) in inputs"
          :key="index"
          v-model="input.value"
          :label="input.label"
          :type="input.type"
      />
      <button>Log in</button>

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
      inputs: [{
        label: 'Email',
        value: '',
        type: 'email'
      },
        {
          label: 'Password',
          value: '',
          type: 'password'
        },
      ],
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
      console.log(this.inputs[0].value, this.inputs[1].value)
    },

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
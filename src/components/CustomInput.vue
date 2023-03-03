<template>
  <label>
    {{ label }}
    <input type="text" v-model="inputValue" @input="handleChange"/>
  </label>
</template>

<script>
export default {
  name: "CustomInput",
  props: ['label', 'modelValue',],

  computed: {
    inputValue: {
      get() {
        return this.modelValue
      },
      set(value) {
        console.log(value)
        this.$emit('update:modelValue', value)
      },
    },
  },

  data() {
    return {
      upperCase: '',
    }
  },
  methods: {
    handleChange (event) {
      this.$emit("customChange", event.target.value.toUpperCase())
    }
  }
}
</script>

<style scoped>

</style>
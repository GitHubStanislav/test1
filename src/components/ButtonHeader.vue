<template>
  <button @click="onClick" :style="{ background: color }" class="btn">{{ text }}</button>
</template>

<script>
export default {
  name: 'ButtonHeader',
  props: {
    text: String,
    color: String
  },
  data() {
    return {}
  },
  methods: {
    onClick() {
      this.$emit('btn-click')
    }
  }
}
</script>

<style scoped></style>

<template>
<div>
  <label :for="control">{{  label }}</label>
  <input
    :id="control"
    :type="inputType"
    autocomplete="off"
    @input="onInput"
  >
</div>
</template>

<script>

export default {
  name: 'TInput',
  props: {
    control: {
      type: String,
      required: true
    },
    label: {
      type: String
    },
    inputType: {
      type: String,
      default: 'text'
    }
  },
  methods: {
    onInput (e) {
      this.$emit('has-input', e.target.value)
    }
  }
}

</script>

<style scoped>
div {
  display: flex;
  flex-direction: column;
}
</style>
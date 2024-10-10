<template>
  <!-- <button @click="onClick">{{ label }}</button> -->
   <button @click="$emit('clicked')">{{  label  }}</button>
</template>

<script>

export default {
  name: 'TButton',
  props: {
    label: String
  },
  methods: {
    onClick (e) {
// custom events .... názvy událostí - kebab-case
      console.log(e)
      this.$emit('clicked')
    }
  }
}


</script>
<style scoped>

</style>
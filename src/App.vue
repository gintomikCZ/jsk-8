<template>
  <TInput
    control="name"
    label="jméno"
    @has-input="onHasInput"
  />
  <div v-if="personName">
    {{ 'Ten člověk se jmenuje ' + personName }}
  </div>
</template>


<script>
import TInput from './components/TInput.vue';
export default {
  name: 'App.vue',
  data () {
    return {
      personName: ''
    }
  },
  methods: {
    onHasInput (payload) {
      this.personName = payload
    }
  },
  components: { TInput }
}

</script>
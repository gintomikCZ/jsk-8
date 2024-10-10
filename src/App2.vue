<template>
  <h1>event listenery</h1>
  <!-- <TComponent :tprops="counter"/> -->
   <!-- vytvořit speciální komponentu, která bude counter zobrazovat -->
  <div class="d-flex">
    <TSquare :label="counter[0]" />
    <TSquare label="ahoj" />
    <TSquare :label="counter[1]" />
  </div>
  <!-- <button @click="increment(0)">první plus</button>
  <button @click="decrement(0)">první minus</button>
  <button @click="increment(1)">druhý plus</button>
  <button @click="decrement(1)">druhý minus</button> -->
  <TButton label="první plus" @clicked="increment(0)"/>
  <TButton label="první minus" @clicked="decrement(0)"/>
  <TButton label="druhý plus" @clicked="increment(1)"/>
  <TButton label="druhý minus" @clicked="decrement(1)"/>
</template>

<script>

import TSquare from '@/components/TSquare.vue'
import TButton from '@/components/TButton.vue'
// Vanilla Javascript
// v-on .... short @
// reactivity

export default {
  name: 'App',
  data () {
    return {
      counter: [0, 0]
    }
  },
  methods: {
    increment (index) {
      // if (par === 1) {

      // } else {
      //   this.counter2 += 1
      // }
      this.counter[index] += 1
    },
    decrement (index) {
      this.counter[index] -= 1
    },
    // increment2 () {
    //   this.counter2 += 1
    // },
    // decrement2 () {
    //   this.counter2 -= 1
    // }
  },
  components: { TSquare, TButton }
}

</script>

<style scoped>
.d-flex {
  display: flex;
}
</style>
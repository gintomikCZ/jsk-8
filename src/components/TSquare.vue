<template>
  <!-- pokud je label číslo a je sudé / párne - pink background -->
  <!-- <div v-if="typeof label !== 'string' && !(label % 2)" class="bg-pink">{{ label }}</div>
  <div v-else>{{ label }}</div> -->

  <div
    :class="{
      'bg-pink': typeof label !== 'string' && !(label % 2)
    }"
  >{{ label }}</div>
</template>

<script>

export default {
  name: 'TSquare',
  props: {
    label: {
      validator: (v) => (typeof v === 'string' || typeof v === 'number') && !Number.isNaN(v)
    }
  }
}

/*

v-bind-class="value"
:class="value"
value je 1) pole s názvy tříd ... ['my-class1', 'my-class2' .....]
  2) value je objekt {
      třída: condition,
      třída2: condition2
  }

const obj = {
  key: 'value'
}

const obj = {
  'my-key': 'value'
}

*/


</script>

<style scoped>
div {
  width: 200px;
  height: 200px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2rem;
  font-weight: bold;
  border: 1px solid #cdcdcd;
}
.bg-pink {
  background: lightpink;
}
</style>
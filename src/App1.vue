<template>
  <h1>jsk - 8</h1>
  <!-- rendrování v cyklu -->
  <!-- <div v-for="fruit in fruits">{{ fruit }}</div> -->
  <!-- <ul>
    <li v-for="fruit in fruits">{{ fruit }}</li>
  </ul> -->

  <!-- <h2>fruits</h2>
  <ul>
    <li v-for="fruit in goods.fruits">{{ fruit }}</li>
  </ul>

  <h2>vegetables</h2>
  <ul>
    <li v-for="vegetable in goods.vegetables">{{ vegetable }}</li>
  </ul>

  <div v-for="item in goods">{{ item }}</div> -->

  <div v-for="item in Object.keys(goods)">
    <h2>{{ item }}</h2>
    <ul v-if="goods[item].length">
      <li v-for="(item2, index) in goods[item]">{{ (index + 1) + '. ' + item2 }}</li>
    </ul>
    <div v-else>{{'na skladě není žádná položka ' + item}}</div>
  </div>


<!-- tomik is child -->
<!-- tomik is adult -->

<div v-if="age < 18">{{ firstname + ' is child' }}</div>
<div v-else>{{ firstname + ' is adult' }}</div>


   <!-- podmíněné rendrování -->

<div v-if="items === 0">Na skladě nemáme žádnou položku</div>
<div v-else-if="items === 1">Na skladě máme 1 položku</div>
<div v-else-if="items < 5 && items > 1">Na skladě máme 4 položky</div>
<div v-else>Na skladě máme 15 položek</div>

</template>

<script>

export default {
  name: 'App',
  data () {
    return {
      firstname: 'Tomik',
      items: 0,
      age: 13,
      goods: {
        fruits: ['hruška', 'banán', 'kiwi'],
        vegetables: []
      }
    }
  }
}

/*
Object.keys(obj) => vrací pole s názvy klíčů (pole stringů) - ['fruits', 'vegetables']
Object.values(obj) => vrací pole s hodnotami
*/

// array.foreach((item, index) => {})

/*

falsy => false
  - false
  - undefined
  - null
  - NaN
  - ''
  - 0
truthy
  - vše ostatní


*/

</script>

<style scoped>

</style>
<script setup>
  import { ref } from 'vue'

  const header = ref('Shopping List App')

  const items = ref([
  {id: 1, label: "10 party hats"},
  {id: 2, label: "2 board games"},
  {id: 3, label: "20 cups"}
  ])

  const itemsObjects = ref({
  'item-1': {id: 1, label: "10 party hats"},
  'item-2': {id: 2, label: "2 board games"},
  'item-3': {id: 3, label: "20 cups"}
  })
</script>

<template>
  <h1>{{ header }}</h1>
  <ul>
    <li v-for="item in items" :key="item.id">
      {{item}}
    </li>
    <li v-for="item in items" :key="item.id">
      {{item.label}}
    </li>
    <li v-for="{id, label} in items" :key="id">
      {{id}} es a {{ label }}
    </li>
    <li v-for="({id, label}, index) in items" :key="id">
      {{id}} es {{ label }} : index = {{ index }}
    </li>
  </ul>
  Print the object
  <ul>
    <li v-for="({id, label}, index) in itemsObjects" :key="id">
      {{id}} es {{ label }} : index = {{ index }}
    </li>
  </ul>
</template>

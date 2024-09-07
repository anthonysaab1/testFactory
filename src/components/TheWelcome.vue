<script setup>
import { ref, watchEffect, computed } from 'vue'
let searchBar = ref('')
let productList = ref('')
let ListOfProducts = ref('')
watchEffect(() => {
  productList.value = computed(() => {
    return ListOfProducts.value.filter((item) => item.name.toLowerCase().includes(searchBar.value))
  })
})
</script>

<template>
  <h1>hello from anthony</h1>
  <input type="text" placeholder="Search" v-model="searchBar" @input="searchValue" />
</template>

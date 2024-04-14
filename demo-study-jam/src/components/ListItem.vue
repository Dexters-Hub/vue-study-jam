<script>
export default {
  props: {
    list: {
      type: Array,
      required: true
    }
  }
}
</script>

<template>
  <h1>Amazing List</h1>
  <ul>
    <li v-for="(item, index) in list" :key="index">{{ item }}</li>
  </ul>
</template>

<script setup>
defineProps({
  title: {
    type: String,
    required: true
  },
  
})
</script>

<template>
  <h1 class="text-4xl font-medium">{{ title }}</h1>
  
</template>
<script>
export default {
  props: {
    user: {
      type: Object,
      required: true
    }
  },
  emits: ['evaluate']
}
</script>

<template>
  <div class="user-card">
    <h1>{{ user.name }}</h1>
    <p>{{ user.email }}</p>
    <button @click="$emit('evaluate')">Evaluate</button>
  </div>
</template>

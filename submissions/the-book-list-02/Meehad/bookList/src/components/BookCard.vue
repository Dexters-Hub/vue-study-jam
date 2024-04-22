<template>
  <div class="card">
    <slot></slot>
  </div>
</template>

<script>
export default {
  setup() {
    return {}
  }
}
</script>

<style>
.card {
  width: 300px;
  border: 1px solid #ccc;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}
</style>
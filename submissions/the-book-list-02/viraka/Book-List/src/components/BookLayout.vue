<template>
  <header>
    <slot name="header"></slot>
  </header>
  <main>
    <div class="container">
      <slot name="form"></slot>
      <slot name="list"></slot>
    </div>
  </main>
</template>

<script setup></script>

<style scoped>
header {
  text-align: center;
  padding: 10px;
  background-color: #f5f5f5;
  color: #333;
  border-bottom: 1px solid #ccc;
}

main {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
}

.container {
  max-width: 800px;
  width: 100%;
  padding: 20px;
}
</style>

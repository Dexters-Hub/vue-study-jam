<template>
  <div class="container">
    <h1>My Books</h1>
    <ul>
      <li v-for="(book, index) in books" :key="index" class="book">
        <h2>{{ book.title }}</h2>
        <p>Author: {{ book.author }}</p>
        <p>Genre: {{ book.genre }}</p>
        <p>Year: {{ book.year }}</p>
        <button @click="$emit('setFavourite', index)" class="favourite">
          <font-awesome-icon :icon="book.favourite ? solidStar : faStar" class="yellow" />
        </button>
        <button @click="$emit('removeBook', index)" class="remove">Remove</button>
      </li>
    </ul>
  </div>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { faStar } from '@fortawesome/free-regular-svg-icons'
import { faStar as solidStar } from '@fortawesome/free-solid-svg-icons'
const { books } = defineProps({
  books: {
    type: Array,
    required: true
  }
})
const $emit = defineEmits(['setFavourite', 'removeBook'])
</script>

<style scoped>
.container {
  max-width: 800px;
  width: 100%;
  padding: 20px;
}

h1 {
  margin-bottom: 20px;
}

.book {
  background-color: #f5f5f5;
  padding: 16px;
  margin-bottom: 10px;
  border-radius: 5px;
  list-style: none;
  box-shadow: 0 0 6px rgba(0, 0, 0, 0.15);
}

.favourite {
  padding: 5px;
  background-color: transparent;
  border: none;
  cursor: pointer;
}

.remove {
  padding: 5px 10px;
  border-radius: 5px;
  border: none;
  background-color: #f44336;
  color: white;
  cursor: pointer;
  float: right;
}
</style>

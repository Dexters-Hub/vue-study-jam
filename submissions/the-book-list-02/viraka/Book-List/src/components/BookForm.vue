<template>
  <form @submit.prevent="addBook">
    <label for="title">Title</label>
    <input type="text" id="title" name="title" placeholder="Title" required />

    <label for="author">Author</label>
    <input type="text" id="author" name="author" placeholder="Author" required />

    <label for="genre">Genre</label>
    <input type="text" id="genre" name="genre" placeholder="Genre" required />

    <label for="year">Year</label>
    <input type="number" id="year" name="year" placeholder="Year" min="1900" required />

    <button type="submit">Add Book</button>
  </form>
</template>

<script setup>
import { defineEmits } from 'vue'
const $emit = defineEmits(['addBook'])

const addBook = () => {
  const title = document.getElementById('title').value
  const author = document.getElementById('author').value
  const genre = document.getElementById('genre').value
  const year = document.getElementById('year').value

  $emit('addBook', { title, author, genre, year, favourite: false })

  document.getElementById('title').value = ''
  document.getElementById('author').value = ''
  document.getElementById('genre').value = ''
  document.getElementById('year').value = ''
}
</script>

<style scoped>
label {
  margin-bottom: 5px;
}

input {
  margin-bottom: 10px;
  padding: 5px;
  border-radius: 5px;
  border: 1px solid #ccc;
  width: 100%;
}

button {
  padding: 5px 10px;
  border-radius: 5px;
  border: none;
  background-color: #4caf50;
  color: white;
  cursor: pointer;
}
</style>

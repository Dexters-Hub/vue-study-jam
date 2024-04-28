<script setup>
import BookList from './components/BookList.vue'
import BookForm from './components/BookForm.vue'
import BookLayout from './components/BookLayout.vue'
import { ref, watch, computed } from 'vue'
const books = ref([
  {
    title: 'The Alchemist',
    author: 'Paulo Coelho',
    genre: 'Theory',
    year: 1988,
    favourite: true
  },
  {
    title: 'The Lord of the Rings',
    author: 'J. R. R. Tolkien',
    genre: 'Fantasy',
    year: 1954,
    favourite: false
  },
  {
    title: 'The Da Vinci Code',
    author: 'Dan Brown',
    genre: 'Mystery',
    year: 2003,
    favourite: false
  },
  {
    title: 'The Hobbit',
    author: 'J. R. R. Tolkien',
    genre: 'Fantasy',
    year: 1937,
    favourite: false
  }
])

const header = ref('BookList')

watch(
  books,
  () => {
    header.value = `${books.value[books.value.length - 1].title}`
  },
  { deep: true }
)
const bookLength = computed(() => {
  return books.value.length
})
function addBook(book) {
  books.value.push(book)
}
function setFavourite(index) {
  books.value[index].favourite = !books.value[index].favourite
}

function removeBook(index) {
  books.value.splice(index, 1)
}

console.log(books.value)
</script>

<template>
  <BookLayout>
    <template v-slot:header>
      <div class="wrapper">
        <h1>{{ header }}</h1>
        <p>Manage your favorite books</p>
      </div>
    </template>
    <template v-slot:form>
      <BookForm @addBook="addBook" />
    </template>
    <template v-slot:list>
      <BookList :books="books" @setFavourite="setFavourite" @removeBook="removeBook" />
      <p class="message">listed {{ bookLength }} books</p>
    </template>
  </BookLayout>
</template>

<style scoped>
* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

.wrapper {
  text-align: center;
}

.message {
  margin-top: 10px;
  float: right;
  font-weight: bold;
  color: rgba(0, 0, 0, 0.581);
}
</style>

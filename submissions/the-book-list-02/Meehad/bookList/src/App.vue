<script>
import BookList from './components/BookList.vue'
import BookForm from './components/BookForm.vue'
import BookCard from './components/BookCard.vue'

export default {
  components: {
    BookList,
    BookForm,
    BookCard,
  },
  data() {
    return {
      books: [],
      latestBook: 'adujeevitham'
    }
  },
  methods: {
    handleAddBook(newBook) {
      this.books.push(newBook)
      this.latestBook = newBook.bookname
    }
  },
  watch: {
    books: {
      bookcount(newbooks) {
        if (newbooks.length > 0) {
          this.latestBook = newbooks[newbooks.length - 1].bookname
        }
      },
      deep: true
    }
  },
  computed: {
    countbook() {
      return this.books.length + 1
    }
  }
}
</script>

<template>
  <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />
  <h1>{{ latestBook }}</h1>
  <h3>Total number of books: {{ countbook }}</h3>
  <BookForm @add-book="handleAddBook"></BookForm>
  <h3>Books List</h3>
  <div class="wrapper">
    <BookCard>
      <BookList name="adujeevitham" author="blessy" genre="survival" year="2006"
    /></BookCard>
    <BookCard>
      <p v-for="(book, index) in books" :key="index">
        <BookList
          :name="book.bookname"
          :author="book.bookauthor"
          :genre="book.bookgenre"
          :year="book.bookyear"
        />
      </p>
    </BookCard>
  </div>
</template>

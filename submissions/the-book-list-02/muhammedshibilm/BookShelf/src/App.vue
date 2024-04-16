<script>
import BookList from './components/BookList.vue'
import BookForm from './components/BookForm.vue'
import BookLayout from './components/BookLayout.vue'

export default {
  name: "App",
  components: {
    BookList,
    BookForm,
    BookLayout

  },
  data() {
    return {
      books: [],
      latestbook: ''
    }
  },
  methods: {
    sendBook(book) {
      console.log(book)
      this.books.push(book)
    },

  },
  watch: {
    books: {
      handler: function (books) {
        this.latestbook = books[books.length - 1]
      },
      deep: true
    }
  }
};
</script>

<template>
  <BookLayout>
    <template v-slot:header>
      <header class="bg-gray-800 text-white p-4">
        <h1 class="text-2xl font-bold">Book Library</h1>
      </header>
    </template>
    <template v-slot:frompage>
      <BookForm @addBook="sendBook" />
    </template>
    <template v-slot:latestbook>

      <h2 v-if="latestbook" class="text-xl shadow  bg-white mx-2 my-2 rounded inline  font-bold p-3">Latest Book: <span
          class="text-neutral-500">
          {{
            this.latestbook['title'] }}
        </span>
      </h2>

    </template>
    <template v-slot:booklist>
      <BookList :booklist="books" />
    </template>
  </BookLayout>
</template>

<style></style>

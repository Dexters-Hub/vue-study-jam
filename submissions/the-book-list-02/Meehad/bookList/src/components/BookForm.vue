<script>
export default {
  data() {
    return {
      bookname: '',
      bookauthor: '',
      bookgenre: '',
      bookyear: 0
    }
  },
  methods: {
    addBook() {
      if (this.bookname && this.bookauthor) {
        this.$emit('add-book', {
          bookname: this.bookname,
          bookauthor: this.bookauthor,
          bookgenre: this.bookgenre,
          bookyear: this.bookyear
        })
        this.bookname = ''
        this.bookauthor = ''
        this.bookgenre = ''
        this.bookyear = 0
      }
    }
  }
}
</script>

<template>
  <h2>Add a Book</h2>
  <form @submit.prevent="addBook">
    <label for="bookname">Name:</label>
    <input type="text" id="bookname" v-model="bookname" />
    <label for="bookauthor">Author:</label>
    <input type="text" id="bookauthor" v-model="bookauthor" />
    <label for="bookgenre">Genre:</label>
    <input type="text" id="bookgenre" v-model="bookgenre" />
    <label for="bookyear">Year:</label>
    <input type="number" id="bookyear" v-model="bookyear" />
    <button type="submit">Add Book</button>
  </form>
</template>
<script>
export default {
    name: "BookForm",
    data() {
        return {
            title: '',
            author: '',
            genres: '',
            year: 0,
        }
    },
    methods: {
        addBook() {
            const book = {
                title: this.title,
                author: this.author,
                genres: this.genres,
                year: this.year
            }
            this.$emit('addBook', book)
        }

    }
}
</script>
<template>
    <div class="mx-2 my-2">
        <h2 class="text-2xl py-2 font-bold">Add Books</h2>
        <div class="grid md:grid-cols-6 sm:grid-cols-3 gap-4">
            <div class="col-span-2">
                <input type="text" v-model="title" placeholder="Book Title" class="border p-2 w-full">
            </div>
            <div>
                <input type="text" v-model="author" placeholder="Author" class="border p-2 w-full">
            </div>
            <div>
                <input type="text" v-model="genres" placeholder="Genres" class="border p-2 w-full">
            </div>
            <div>
                <input type="number" v-model="year" placeholder="Year" class="border p-2 w-full">
            </div>
            <div>
                <button @click="addBook"
                    class="bg-indigo-500 shadow-lg text-white rounded shadow-indigo-500/50 p-3">click
                    me</button>
            </div>
        </div>
    </div>
</template>
<style></style>
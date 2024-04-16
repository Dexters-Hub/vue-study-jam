<script>
export default {
    name: "BookList",
    props: {
        booklist: Array,
    },
    computed: {
        totalBooks() {
            return this.booklist.length
        }
    }
}
</script>
<template>
    <div class="mx-2 my-2">
        <div class="grid grid-cols-6 gap-4 mx-2">
            <div class="col-span-2">
                <h2 class="text-2xl py-2 font-bold mt-2">List Books</h2>
            </div>
            <div class="col-span-4 text-end">
                <h2 class="text-2xl py-2 font-bold">Total: {{ totalBooks }}</h2>
            </div>
        </div>
        <div class="grid md:grid-cols-3 gap-4">
            <div v-for="book in booklist" :key="book.title" class="bg-white p-4 shadow-md">
                <h2 class="text-xl font-bold">Name: <span class="text-neutral-600">{{ book.title }}</span></h2>
                <p class="text-sm font-bold">Author: <span class="text-neutral-400">{{ book.author }}</span></p>
                <p class="text-sm font-bold">Genres: <span class="text-neutral-400">{{ book.genres }}</span></p>
                <p class="text-sm text-end font-bold">Year: <span class="text-stone-500">{{ book.year }}</span></p>
            </div>
        </div>
    </div>

</template>
<style></style>
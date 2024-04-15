<script>
export default{
    emits: ['search'],
    data() {
        return {
            search: ''
        }
    },
    methods:{
        searchMovies(name){
            console.log("SearchComp running search", name)
            this.search = name
        }
    }
}
</script>
<template>
    <div class="flex justify-start">
        <input type="text" class="border border-gray-300 p-2 rounded-lg" placeholder="Search movie" @input="searchMovies($event.target.value)">
        <button class="bg-blue-500 text-white px-4 py-2 rounded-lg border" @click="$emit('search', search)">Search</button>
    </div>
</template>